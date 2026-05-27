---
layout: post
title: "A Love Letter to Neovim"
date: 2026-05-26 00:00:00 -0400
categories: blog
tags: [neovim, vim, developer-tools, productivity]
---

![Code editor open in a focused developer workspace](https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=1200)

I started using Vim in 2011. Not because I was trying to make a point, and definitely not because I knew what I was doing. I was probably following some blog post, copying a `.vimrc`, and wondering why pressing `j` moved the cursor instead of typing a letter.

The first week was rough. The first month was weird. Then Vim's model started to make sense, and every other editor began to feel like it had a layer of padding between me and the code.

All these years later, Neovim is still the tool I trust the most. I have used VS Code. I have used JetBrains IDEs. I have played with Sublime, Atom, Zed, and whatever else was having a moment. Some of them are genuinely good. JetBrains tools are absurdly capable. VS Code won because it is good enough for almost everyone and easy to extend.

I still pick Neovim.

The reason is simple: Neovim keeps up with the way I work. Not always with the speed I type, because typing is not really the point. Editing code is mostly moving around, changing small pieces, deleting the wrong abstraction, reshaping a function, jumping between files, running tests, checking diagnostics, and doing that loop again. Neovim is built around that loop.

Most editors treat text like a document and the keyboard like an input device. Vim treats editing like a language. That sounds a little dramatic until you spend enough time with it. `ci"` means change inside quotes. `dap` deletes a paragraph. `.` repeats the last change. Macros let you teach the editor a tiny routine once and replay it across a file. Text objects let you operate on meaning instead of counting characters.

That is the part people miss when they say Vim is just keyboard shortcuts. It is not a bag of shortcuts. It is a grammar.

Once that grammar gets into your hands, the editor becomes a lot less noisy. You stop dragging the mouse across code. You stop clicking through sidebars just to find a file. You stop reaching for a command palette for things you do fifty times a day. The common actions become small, direct movements.

Neovim is superior to other editors for me because it does not force my work through someone else's idea of a workflow. GUI-first editors always seem to have an opinion about where everything belongs. The explorer goes here. The terminal goes there. The git panel gets its own shape. The debugger has its own little world. Before long, the editor is a cockpit.

Neovim starts with a buffer and lets me decide what earns a spot around it. If I want a file tree, I can add one. If I want fuzzy finding, I can use Telescope, fzf-lua, or whatever fits. If I want Git integration, Fugitive is still one of the best pieces of software ever written. If I want LSP, diagnostics, formatting, snippets, Treesitter, test runners, and completion, Neovim handles all of that without turning into a slow Electron dashboard.

That matters more than people admit. Speed is not just about startup time, although Neovim is great there too. Speed is also about trust. When I press a key, I expect the editor to respond right now. When I open a large file, I do not want the whole UI to sigh and think about it. When I am SSH'd into a machine, pairing in a tmux session, or fixing something from a tiny terminal window, I want the same editor brain I use every day.

Neovim gives me that. Local project, remote server, quick config change, big Rails app, tiny shell script, markdown post like this one. Same movements. Same commands. Same muscle memory.

That consistency adds up over a career.

Another thing I love is that my setup belongs to me. My config is just files in git. I can read it. I can break it. I can delete half of it when I realize I do not need a plugin anymore. There is no mystery settings database, no synced account state that I only half understand, no extension doing something strange in the background because a checkbox changed three releases ago.

This is where Neovim feels different from the modern editor world. A lot of tools want to become the place where everything happens. Neovim is happy being the sharp part of a larger system. It works with the shell instead of trying to replace it. It works with tmux, ripgrep, git, language servers, formatters, linters, and test runners. It does not need to own the whole desk.

That is also why it has lasted. I have watched editors come and go since 2011. I have watched whole ecosystems rise around extensions, themes, marketplaces, and AI panels. Vim was already old when I started using it, and Neovim managed to modernize the parts that needed it without throwing away the reason people cared in the first place.

Lua made configuration nicer. The plugin ecosystem got much better. Built-in LSP brought IDE features into the editor without making it feel bloated. Treesitter made syntax highlighting and code awareness feel modern. Lazy.nvim made plugin management fast and boring, which is exactly what plugin management should be.

But the core reason I love it has not changed. Neovim rewards time spent learning it. Not in a gatekeeping way. I do not care if someone else wants to use VS Code. Use whatever lets you do good work. But Neovim is one of the rare tools where a small thing learned years ago is still useful today.

You learn a motion, and it helps forever. You write a macro, and a boring edit disappears. You discover a text object, and some annoying refactor becomes easy. You tune one command, and it becomes part of your hands. The editor gets better because you got better, not because a company shipped a new sidebar.

That is a big part of productivity that is hard to measure. It is not just "I saved five seconds here." It is the reduced friction across thousands of small edits. It is the lack of context switching. It is being able to jump from code to tests to git diff to search results without feeling like I changed rooms. It is keeping my attention on the problem instead of on the tool.

Neovim also makes me more deliberate. Since the editor is so programmable, I end up shaping my workflow instead of just accepting defaults. If something is annoying twice, I can usually fix it. A mapping, a command, a small Lua function, a better plugin, or sometimes deleting a plugin entirely. The setup evolves with the way I actually work.

I think that is why I am still attached to it after all this time. It is not nostalgia. I am not using Neovim because I learned it young and refuse to move on. I use it because when I know what change I want, Neovim puts very little between the thought and the edit.

After fifteen years with Vim and Neovim, I honestly cannot imagine my career with a different editor at the center of it. The languages changed. The frameworks changed. The machines got faster. The industry reinvented the same five ideas a few times. Through all of that, this strange little modal editor kept being the place where I did my best work.

That is enough for me.
