---
layout: post
title: Getting ctags to work with Elixir (in Neovim)
description: How to add ctags support for elixir
tags: elixir ctags
---

tldr: If you're using universal-ctags and want elixir support:
 - navigate to, or create, ~/.ctags.d
 - inside, create elixir.ctags file
 - copy and paste the contents of the [elixir-ctags](https://github.com/mmorearty/elixir-ctags){:target="_blank"} file into `~/.ctags.d/elixir.ctags`.
 - run ctags -R in your project directory

(Note: I've gone back to Spacemacs, but leaving here in case it's useful for future me and others.)

I saw this post: ['Vim is the Perfect IDE'](http://coderoncode.com/tools/2017/04/16/vim-the-perfect-ide.html){:target="_blank"} on the CoderOnCode blog.

CoderOnCode also appears to be an elixir programmer. Lo and behold CoderOnCode has included ctags as part of the tools used for elixir programming.

For those of you who do not know what a 'ctags' is, briefly, ctags (ctags, exuberant-ctags, universal-ctags, etc.) use regexes (regexi?) to parse the files in your code and identify keywords. This process results in a file (default is the cleverly, yet accurately, named 'tags'). Your editor can then use the contents of this file to display to you the modules, functions, etc. that exist in your codebase.

This is useful for learning an unfamiliar codebase, navigating through a large code base, etc.

Concurrent with this I started to learn ruby. I found that out of the box ruby in vim supported the creation of a tags file (vim-gutentags handled this without me realizing it, I think) and I found myself using the tags - it also added some nice chrome to vim-airline.

With the knowledge that:
- tags are good
- tags are useful
- tags work in ruby in vim

I set off to make this happen in elixir.

Searching the web far and wide all I could find was a package - [elixir-ctags](https://github.com/mmorearty/elixir-ctags){:target="_blank"} - with some cryptic instructions, and the exuberant ctags website which appears to have last been updated around the turn of the last millennium.

It appeared that many, many people struggled to get ctags to work on macOs. But I could not figure out how to get elixir and ctags to work together.

Finally, I came to the realization that I was using universal-ctags. Looking at the documentation for universal-ctags (readthedocs-style) was impenetrable. It did confirm that exuberant-ctags had out-of-the-box support for Erlang and I assumed, by extension, so did universal-ctags, but nothing on elixir.

Then I found the following, seemingly written down for posterity, but not with the goal of helping someone. it said that perhaps the most immediate different b/w exuberant and universal-ctags was that universal relies (or pulls from) a directory `~/.ctags.d` to find any personal settings (such as the file created as a result of following the directions from elixir-ctags) and that such a file should end in `.ctags`.

Putting two and two together, crossing my fingers and closing my eyes, I put the elixir-ctags code into a file `elixir.ctags` and saved it inside ~/.ctags.d/.

I changed directories to my current elixir project and ran the following command in the project root `ctags -R`. Believe it or not, that worked!

When I toggled vim-tagbar, I could see my tags listed out nicely in accordance with CoderOnCode settings and I could navigate back and forth to my heart's content.
