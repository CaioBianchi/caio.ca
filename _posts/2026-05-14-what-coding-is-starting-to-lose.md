---
layout: post
title: "What Coding Is Starting to Lose"
date: 2026-05-14 00:00:00 -0400
categories: blog
tags: [ai, software-development, coding, productivity]
---

I sat down last week to fix a small bug in one of my side projects. Nothing dramatic, just a weird race condition in a background job. Ten years ago this would have been a whole evening. I'd open the code, stare at it, make a change, run the test suite, swear a bit when it failed again, make another change, go for a walk, come back, and eventually land on something that worked.

The weird part is I didn't get that feeling this time. Because I didn't really do it.

![A developer working thoughtfully at a laptop in natural light](https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=820)

I described the problem to the model. It gave me a fix. I pasted it in. The tests passed. Whole thing took twelve minutes. I closed the laptop feeling... fine. Not proud. Not annoyed. Just done.

That gap between "problem exists" and "problem solved" used to be where a lot of the actual experience of being a developer lived. Not every minute of it was fun. Plenty of it was frustrating. But when the fix finally clicked, there was a specific kind of satisfaction that came from having turned it over in your head for a while. You could point at the code and say, without stretching the truth, that you made it do that.

A lot of that texture is thinning out.

The first thing that disappeared was the long, messy parts. The hours where you were just reading code you wrote six months ago and trying to remember why you made certain decisions. AI doesn't need that context. It scans the file and immediately suggests three ways to restructure it. Which is useful, obviously. But it also means fewer of those slow mornings where you're reacquainting yourself with your own work and noticing small improvements you could make along the way.

Then there's the actual writing of the code. I used to love the fiddly parts. Choosing variable names. Deciding how to split a function so the logic felt right when you read it later. Adding comments only where they actually helped. None of that feels particularly necessary when you can just ask for a refactor and get back something that looks clean. The code that comes out is often fine. Sometimes better than what I would have written tired on a Thursday. But it doesn't feel like mine in the same way. It feels like something I approved.

![Code editor open on a clean desk, late afternoon light](https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=820)

The smaller, weirder joys went next. Figuring out how to make a script slightly faster by changing the order of operations. Spending twenty minutes getting a one-line regex exactly right. Realizing you could delete an entire file because the logic belonged somewhere else. Those moments used to happen constantly. Now they happen when I deliberately slow down and ignore the suggestions. Which I do less often than I should.

Even the sense of progress has changed. There used to be a visible path from "this is broken" to "I think I understand what's happening" to "okay, I fixed it." The middle step is where most of the learning used to occur. Now the model often hands you the answer before you've had time to feel confused. You get the resolution without having earned the confusion first. And while that saves time, it also skips the part where you actually get better at noticing similar problems in the future.

I keep hearing people say the real work now is review and direction. That's true, but it still feels different. Reviewing code someone else wrote, even if that someone is a model, doesn't produce the same quiet satisfaction as writing it yourself. You're catching issues, not creating solutions. It's important work. It's just less... rewarding on a personal level.

The bigger projects suffer too. When I finish a feature now, I often have this vague sense that I didn't really build it. I orchestrated it. I described the shape. I accepted some suggestions and rejected others. But the actual construction happened in a different place. And because it happened so fast, there's no accumulated mental map of every corner of the feature. Two weeks later when something breaks, I have to re-read my own code like it's someone else's.

There's also something quieter that went missing. The craft aspect. The part where you care how the code looks even if no one else will ever see it. When you're writing alongside a tool that will happily generate the next thirty lines for you, it becomes easier to treat the whole thing as temporary. Why make it beautiful when you can just ask for a cleanup later? The code becomes more disposable on purpose.

I don't think any of this was the intention. The tools were sold on speed and quality, and they deliver both. But the byproduct is that a lot of the private, internal experience of writing software has been compressed. And some of the best parts of that experience were never fast.

---

None of this means the tools are bad or that we should go back to doing everything by hand. The productivity gains are real and substantial. What used to take a full day of wrestling with boilerplate and context-switching now takes an hour. Teams ship features they would have deprioritized a year ago because the implementation cost dropped. People who are still learning get unstuck faster instead of spending days on syntax they haven't memorized yet. The boring, repetitive work that used to eat entire mornings gets handled in minutes.

![Modern developer workspace with multiple screens and minimal setup](https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=820)

The bigger shift is what becomes possible. A solo developer can now explore ideas that used to require a small team just to get past the first prototype. Experimentation is cheaper. Failure is cheaper too. You can try three different approaches to a hard problem in the same afternoon instead of picking one and hoping. That changes what kinds of projects feel worth attempting.

Most importantly, the high-level thinking and judgment parts of the job have more room. When the mechanical work takes less time, there's genuinely more space for architecture decisions, thinking about users, and deciding what shouldn't be built at all. In that sense the tools reward people who already have taste and experience while also lowering the floor for people who are still acquiring those things.

The challenge is keeping both sides honest. The speed is valuable, but so is the slower process of actually understanding what you're shipping. Using the tools well seems to mean deliberately choosing when to let them run ahead and when to slow down and stay inside the problem yourself. The developers who figure out that balance are the ones who keep the craft part alive while still getting the real productivity wins.