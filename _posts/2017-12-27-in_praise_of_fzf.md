---
layout: post
title: In Praise of the FZF Plugin for Vim
description: the FZF plugin for vim is amazing and you should be using it if you use vim
tags: vim
---

tldr:
The [fzf plugin for vim](https://github.com/junegunn/fzf.vim) is an absolute game-changer. Some things to try:
 - :Files: fuzzy-find (very fast) files in your project
 - :GFiles: fuzzy-find the files in your project that are under version control
 - :Buffers: like :ls but you can again use fizzy-find
 - :Lines: search you project by line of code
 - :BLines: like above but limited to current buffer's contents
 - :Tags: yup, fuzzy-find for ctags
 - :BTags: yup, it's what you think

(Note: I have switched back to Spacemacs, but this plugin is still amazing!)

I can't quite recall how I came across [fzf](https://github.com/junegunn/fzf) and it's [vim plugin](https://github.com/junegunn/fzf.vim). fzf on its own is pretty cool, but the vim-plugin is _**AMAZING**_

I used to use Emacs (specifically Spacemacs) and there is an amazing set of packages: [Counsel, Ivy and Swiper](https://github.com/abo-abo/swiper)

In emacs you need something called a completion engine. This is the interface through-which you interact with emacs (helm and ido are two popular completion packages as well).

Anyway, one of the killer features of Ivy is when you want to search the contents of a file (buffer) you run the swiper command and ivy shows any and all results. When you first start all lines in your code is shown as you have not yet provided something to search for. As you begin to type, the lines that match your search string begin to whittle-down to what you need.

I moved away from Spacemacs, but I longed for Ivy, Counsel and Swiper.

fzf is very close to that same functionality and just like Ivy the plugin is more like an interface I use to interact with vim.

If I want to find a file in my project - :Files.
If I want to find a file in my project under version control - :GFiles
If I want to change buffers - :Buffers
If I want to search for something in my file like I did using Ivy in Spacemacs: :BLines (or :Lines if I want to search across all files in my project)
If I want to navigate to a different module using the info in my tag file - :Tags (this one has saved me hours upon hours)
I can also do that but for just the keyword in the current buffer - :BTags
can't remember that keyboard shortcut? :Maps

Oh yeah...you can create your own commands too!

fzf is a must-have vim plugin. Actually, the developer [junegunn](https://github.com/junegunn) has other great vim plugins. Use the link to browse his repository. I suggest also reading through his .vimrc to see the plugins (his and others) he is using.
