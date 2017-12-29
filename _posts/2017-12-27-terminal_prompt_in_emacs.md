---
layout: post
title: Fix your Shell Prompt in Emacs
description: How to fix your emacs shell prompt if it shows '1337;'
tags: emacs shell
---
tldr
If your shell prompt looks fine in iTerm2, but strange inside emacs shell (specifically, seeing `'1337;Remote Host...CurrentDir'` inside ansi-term or multi-term) try deleting your iterm-shell-integration file.
(see applicable links at bottom of this post)

## The whole story

I've used emacs (spacemacs, specifically) for a number of years now. One day, I fired up a shell inside emacs (I usually use ansi-term) and my prompt was polluted with some strange characters `'1337;Remote Host...CurrentDir=...'`.

I searched the internet far and wide.
I found how to remove the '4m's and other strange characters. But the issue persisted.

I grew so frustrated I decided to leave Spacemacs and use vim (I've always loved vim and use evil-mode for emacs). After several days of setting up vim and tmux and another several days trying to get my theme to work inside tmux, the whole system felt brittle.

I went back to emacs and looked at the prompt - the strange symbols seemed to be where the unicode characters show up when viewed inside iTerm2. I found a way to allow emacs to show unicode inside ansi-term.

Elated, I made that change, fired up emacs, then ansi-term - BAM! my unicode symbols showed correctly, but I still had those lingering '1337 and directory info' showing up.

I decided there were two courses of action:
 - since I don't use Bash, I could tell emacs' ansi-term to use /usr/bash for my shell instead of /usr/zsh; or
 - figure out how to use one prompt when the shell is being run by iTerm and a different one run inside emacs.

I actually tried both, but:
 - I didn't like having to maintain two alias files - one for zsh and one for bash; and
 - I tried to find how to test if I was inside emacs running a shell or not to input into my .zshrc, but could not find a way to make it work.

Frustrated, again, I revised my search terms and held my breath. Finally, I saw something that said the issue could be that I was using iTerm2's iterm-shell-integration. All I had to do was run `rm ~/.iterm2_shell_integration.zsh` and my prompt no longer had any extraneous symbols (actually, i used 'trash' instead of 'rm' - 'rm' is unecesarily dangerous).

This also explained why one day my prompt was fine and the next day it was messed-up. When you install iterm2 it does not install the shell-integration automatically. One day I must have decided to install it, causing my emacs shell prompt to report strange characters.


### Links:
 - [my isssue: seeing '1337;Remote Host...CurrentDir=...'](https://redd.it/5p3njk)
 - Typical advice for fixing characters in emacs shell prompt:
   - [color escape codes poluting emacs shell prompt](http://www.joshstaiger.org/archives/2005/07/fixing_garbage.html)
   - [seeing '4m' in prompt](https://stackoverflow.com/questions/8918910/weird-character-zsh-in-emacs-terminal)
 - [Spacemacs](http://spacemacs.org)
 - [Neovim](https://neovim.io)
 - [information about iterm2-shell-integration](https://www.iterm2.com/documentation-shell-integration.html)
 - show unicode in emacs shell
 ```lisp
(defun my-term-use-utf8 ()
  (set-buffer-process-coding-system 'utf-8-unix 'utf-8-unix))
(add-hook 'term-exec-hook 'my-term-use-utf8)
