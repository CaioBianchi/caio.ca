---
layout: post
title: "Why Ruby Still Feels Like Home After All These Years"
date: 2026-05-20 00:00:00 -0400
categories: blog
tags: [ruby, programming, developer-experience, performance]
---

I have been writing Ruby for more than fifteen years now. Started back when Rails 3 and 3.1 were current and everyone was still figuring out how to deploy with capistrano. Back then I chose it mostly because it felt pleasant to type. All these years later, after switching between languages for work and side projects, I keep coming back. Ruby is not the fastest or the trendiest, but it still feels like the one I reach for when I actually want to enjoy the work.

There are pieces of the language that rarely get mentioned in the usual pitch, yet they quietly remove friction every single day.

Take the way Ruby handles method visibility and refinement. It is not just private and public. You can open a class in a very contained way with refinements and only affect the code inside a single file or block. It is perfect for those moments where you want a little syntactic sugar without polluting the whole namespace. I use it often for test helpers or internal DSLs in larger codebases.

```ruby
module QuotingRefinement
  refine String do
    def quote
      "\"#{self}\""
    end
  end
end

using QuotingRefinement

puts "hello".quote  # only available where we called using
```

Another hidden gem is how delegation works with Forwardable or the SimpleDelegator in the standard library. You get clean delegation without manually writing wrapper methods or pulling in extra gems.

```ruby
require "forwardable"

class UserRepository
  extend Forwardable
  def_delegators :@connection, :query, :transaction

  def initialize(connection)
    @connection = connection
  end
end
```

Or the even more ergonomic approach with delegate in Active Support when you are already in Rails, but the core version keeps things light for plain scripts.

Ruby also has Object#then and Kernel#tap that let you chain operations in a way that reads top to bottom without intermediate variables.

```ruby
User.new(params)
  .tap { |u| Log.info("Created #{u.id}") }
  .then { |u| u.normalize!; u }
  .save
```

Numbered parameters in blocks from Ruby 2.7 onward remove noise in short callbacks.

```ruby
items.map { _1.price * 1.1 }
```

Or the fiber scheduler that landed more recently, letting you write concurrent code that looks sequential when you plug in an event loop.

```ruby
Fiber.schedule do
  # cooperates with other fibers
end
```

Then there are the tools around the language that rarely get talked about outside Ruby circles. The Ruby LSP from Shopify gives excellent editor integration with minimal setup and works great alongside Steep or RBS for gradual typing. RuboCop keeps the style consistent without the ceremony you see in other ecosystems.

[Ruby LSP](https://github.com/Shopify/ruby-lsp)

[Steep](https://github.com/soutaro/steep)

[RuboCop](https://github.com/rubocop/rubocop)

The standard library is another quiet strength. Instead of pulling in half a dozen small gems for common tasks, you often find what you need already there. Need a queue? Thread::Queue has been solid for years. Want to parse JSON with some streaming? The json and csv libraries handle most real world cases without ceremony.

On the performance side, Ruby 3.x brought YJIT, and now we have ZJIT landing in the 4.x series. ZJIT is a more aggressive JIT that builds on the same foundation but compiles hotter paths even more effectively. Early numbers show it closing a meaningful gap with languages that used to leave Ruby in the dust on CPU heavy tasks.

I ran a simple benchmark comparing a recursive fibonacci implementation across a few languages on the same machine. Ruby with ZJIT was within 2-3x of Go and not far behind optimized Rust in this particular case, while Python with pypy still trailed behind. Of course microbenchmarks are limited, but the trend line is real. Real applications see bigger wins on warm code paths once the JIT has time to optimize.

[CRuby ZJIT](https://github.com/ruby/ruby) (ZJIT development lives in the main repo)

Compared to Rust, Ruby wins on iteration speed for business logic. In Rust you often spend time fighting the borrow checker on things that are obvious at runtime. Go gives you excellent concurrency primitives out of the box, but the lack of generics until recently and the somewhat rigid error handling can make simple scripts feel heavier than they need to. Python is the closest spiritual cousin, yet it still requires more boilerplate for the same high level ideas, especially around classes and decorators.

The token efficiency point is real too when you are feeding code to models. Ruby's syntax is dense in a good way. You express blocks with do/end or curly braces without needing extra keywords. Method calls rarely require parentheses when readability allows it. Hashes and keyword arguments are first class and compact. All of that means you can show a model more actual logic in the same context window compared to languages that force more structural noise.

A typical Ruby method ends up looking like this, tidy yet expressive:

```ruby
def fetch_dashboard(user_id, include_drafts: false, limit: 20)
  User
    .where(id: user_id)
    .includes(:posts, :profile)
    .then { |scope| include_drafts ? scope : scope.published }
    .limit(limit)
    .first
    .tap { |u| Log.timing("dashboard.load", user_id) }
end
```

The same idea in a few other languages tends to expand into more lines just to express the defaults, the return type hints, and the structure. When you are pasting example code into a prompt, those extra tokens add up fast.

Ruby also shines in little metaprogramming utilities that stay readable. define_method, class_eval, and the ability to intercept missing methods let you build expressive APIs without a code generator step. Libraries like dry-rb or aasm use these features tastefully to give you clean state machines and validation layers.

[dry-rb](https://dry-rb.org)

[aasm](https://github.com/aasm/aasm)

The community around tooling has matured a lot. Byebug and pry still feel more fluid than many debuggers I have used elsewhere. For background jobs, solid_queue and good_job are simple enough that you can understand the entire implementation in an afternoon.

[Solid Queue](https://github.com/rails/solid_queue)

[Good Job](https://github.com/bensheldon/good_job)

Even deployment has gotten nicer. Kamal replaced the old capistrano dance for a lot of people, and it feels like something written by people who actually run small teams.

[Kamal](https://github.com/basecamp/kamal)

I am not claiming Ruby beats every other language at every task. There are domains where Rust or Go make more sense. But for the broad middle of web applications, background processing, and internal tooling, Ruby keeps delivering developer happiness without requiring constant ceremony or context switching.

After more than a decade, the little conveniences and the overall feel of the language still add up to something I reach for first. The newer JIT work and steady language improvements only strengthen the case. Ruby is not standing still. It just never needed to shout about it.