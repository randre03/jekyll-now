---
layout: post
title: Getting ctags to work with Elixir (in Neovim)
---

# Getting ctags to work for elixir in vim

(Note: I've gone back to Spacemacs, but leaving here in case it's useful for future me and others.)

### tldr: If you're using universal-ctags and want elixir support:
 - navigate to, or create, ~/.ctags.d
 - inside, create elixir.ctags file
 - copy and paste the contents of the elixir-ctags file into elixir.ctags
 - run ctags -R in your project directory

I saw this post: 'Vim is the Perfect IDE' at http://coderoncode.com/tools/2017/04/16/vim-the-perfect-ide.html on the CoderOnCode blog about setting up vim as an "IDE". Not sure it's necessary for vim to 'be and IDE', perhaps a topic for another day.

Regardless, CoderOnCode also appears to be an elixir programmer (if Rust programmers are 'rustaceans' what does that make an elixir programmer?). Lo and behold CoderOnCode has included ctags as part of the tools used for elixir programming.

for those of you who do not yet know what a 'ctags' is, briefly, ctags (ctags, exuberant-ctags, universal-ctags, etc.) use regexes (regexi?) to parse the files in your code and identify keywords. This process results in a file (default is the cleverly, yet accurately, named 'tags'). Your editor can then use the contents of this file to display to you the modules, functions, etc. that exist in your codebase.

This is useful for learning an unfamiliar codebase, navigate trough a large code base, etc.

Anyway, CoderOnCode showed this could be done for elixir. At first I set-up my .vimrc to use this code verbatim, expecting it to work (actually I use neovim which ascribed to the BLANK protocol and therefore I put the code in ~/.config/nvim/init.vim). That, of course, is a code smell in vim.

I left it alone, then I realized I was not using it and just removed it from init.vim.

Concurrent with this I started to learn ruby. I found that out of the box ruby in vim supported the creation of a tags file (vim-gutentags handled this without me realizing it, I think) and I found myself using the tags - it also added some nice chrome to vim-airline.

With the knowledge that:
- tags are good
- tags are useful
- tags work in ruby in vim

I set off to make this happen in elixir.

Searching the web far and wide all I could find was a package - elixir-ctags - with some cryptic instructions, and the exuberant ctags website which appears to have last been updated around the turn of the last millennium.

It appeared that many, many people struggled to get ctags to work on macos. But I could not figure out how to get elixir and ctags to work together.

Finally, I came to the realization that I was using universal-ctags. Looking at the documentation for universal-ctags (readthedocs-style) was impenetrable. It did confirm that exuberant-ctags had out-of-the-box support for Erlang and I assumed, by extension, so did universal-ctags, but nothing on elixir.

Then I found the following, seemingly written down for posterity, but not with the goal of helping someone. it said that perhaps the most immediate different b/w exuberant and universal-ctags was that universal relies (or pulls from) a directory /.ctags.d to find any personal settings (such as the file created as a result of following the directions from elixir-ctags) and that such a file should end in .ctags.

putting two and two together, crossing my fingers and closing my eyes, I put the elixir-ctags code into a file elixir.ctags and save it inside ~/.ctags.d.

Bravely, I changed directories to my current elixir project and ran the following command in the project root `ctags -R`. Believe it or not, that worked!
When I toggled vim-tagbar, I could see my tags listed out nicely in accordance with CoderOnCode settings and I could navigate back and forth to my heart's content.
