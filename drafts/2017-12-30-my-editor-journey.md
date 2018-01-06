---
layout: post
title: My Editor Journey
description: In search for my own personal "one true editor" I've mostly learned I like configuring editors
tags: personal emacs vim editors
---

tldr:
 - In search for my own personal "one true editor" I've mostly learned I like configuring editors
 - Including {{{INCLUDE LINKS TO EACH}}}:
   - Emacs (vanilla and the Spacemacs distro)
   - Vim and Neovim
   - Eclipse
   - Notepad (default windows text editor)
   - GEdit (default Ubuntu text editor)
   - Sublime Text 2 and 3
   - VSCode
   - Visual Studio IDE
   - Atom
   - intelliJ IDEA and WebStorm IDEs (as well as language-specific plugins like [Cursive](https://cursive-ide.com/){:target="_blank"})

## A Slightly Longer tldr
**Warning:** This is written as a story, with a lot of details that you don't ncessarily need to know. Here's the abridged version:
 - I struggled with  the likes of Notepad and GEdit at first, but while I knew they were lacking, I didn't know of the existience of anything better.
 - I did try Eclispe (we did mostly Java programming in college), but it was far too complex to learn in littel time and the things we were developing were not large enough to warrant its power.
 - After being away from programming for a decade, I suddenly found a world dominated by JavaScript and I quickly adopted Sublime Text.
 - ST was fine, but I was really put off by being at the whim of a single developer and a period of stagnant development of over a year.
 - I had always been intrigued by Vim, and dove in head-first. I learned to love modal editing and require it out of any editor I use now or in the future.
 - At the time I was getting up to speed with Vim, I started learing some of the Lisp derivatives - most notably Clojure.
   - I love [Tim Pope's Vim pugins](https://github.com/tpope){:target="_blank"} as well as those by junegunn (especially fzf - [here's a link to my write-up]({% post_url 2017-12-27-in_praise_of_fzf%}){:target="_blank"})
   - I really liked Pope's [vim-fireplace](https://github.com/tpope/vim-fireplace){:target="_blank"} plugin, but this was early in its development and I could not get it to work reliably for me - I'll be the first to admit this could have been entirely my fault.
 - As I was getting into Clojure, the "natural" choice was Emacs, but there had to be a way to use my vim-fu.
 - Enter Spacemacs, a flexible, yet opinionated emacs setup that proclaims: *"The best editor is neither Emacs or Vim, it's Emacs **and** Vim!"*
 - Spacemacs is what I currently use, although I have had daliances with:
   - Atom
   - Neovim
   - VSCode
   - intelliJ and its variants
 - I really love the flexibility that Spacemacs offers, that it's open source, and I can configure it **in any way** I want.

## Origin Story
 I've always been interested in software programming - the thought of creating something that runs on a computer that can be useful to someone is so exciting to me. Ever since I took my first (and only) high School programming class and concurrently learned how to program the TI-85 calculator, I've been hooked! Ever since then, I have been searching for an editor that works for me.

## Early Days: Notepad, Eclipse and Emacs
 In college, while enrolled in the School of Management, I studied Finance, Accounting and Computer Science. As was typical in the early 2000s, the Java was the language we used to learn programming concepts and techniques (hey, we were young and didn't know any better...not sure what our professors' excuse was). I really had no concept of an "IDE" or even editors with features that can help you with complex things like:
  - managing brackets
  - syntax highlighting
  - linting / debugging

As a result, I recall being highlighy frustrated try to program using the Windows Notepad program. I searched the internet and learned of Eclispe and figured that would practically write my code for me. I downloaded it once or twice, but quickly grew annoyed - it clearly was (is) very powerful, but too complex. And given Comp Sci was not the only subject I was studying, I could not afford the time to learn it.

I can't recall how I learned of the existence of Emacs - perhaps it was a professor mentioing it in passing - but the thought of an editor as old and storied as Emacs was very enticing. I recall installing it on my dual-boot Windows/Ubuntu machine, reading through some of the help files and having no idea how this thing was supposed to help me. Also, when I opened emacs, there was always a horizontal split. I could never understand why there was a second window, but it was always there.

Only later on in life (see below) did I learn of emacs major and minor modes, how they can be added and manipulated to suite your programming language and environment. I also learned later on, that Java support in emacs is available, but perhaps not as fully-featured as what one gets in the aforementioned Eclipse.

I wrapped up my studies with  a combination of Notepad and GEdit (GEdit added a lot that Notepad was missing, but I never really cared for it). By necessity I learned how to (somewhat) use java's command line debugger and was able to write a half-way decent graphing calculator.

## Return of the Jedi
After college, I left programming behind, focused on my job, moved around, got married and started a family. Ten years after graduation, I was looking for a hobby and decided to get back into programming. At this point in time JavaScript had become **HUGE** and NodeJS was starting to take the world by storm. Anytime you're learning about JavaScript, you can't help but cross paths ro learn something from Wes Bos ((INSRT LINK)). Wes was big into Sublime Text, I picked up his book, and got customizing. *I think this is when I found my love of editor configuration.*

I found all of those websites that have lists of "The Sublime Text Plugins All Web Developers Need" and "The Sublime Text Plugins All Developers Need" and any ones recommended by people I looked up to and any ones that solved the current problem I was having and ... then everything went to hell.
 - Errors started occurring, errors that I could not track down
 - keyboard shortcuts woulnd't work as expected
 - Sublime Text development slowed to a glacial pace

That last one _REALLY_ bothered me. Sublime Text is a proprietary piece of software subject to the whims, desires, biases and life of (what I think is) one, solitary developer.

Since coming back to software development I had been hearing more and more about Vim. Vim was new, exciting, different and an awakening.

## The Great Awakening
