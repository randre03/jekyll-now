---
layout: post
title: Speed up Navigagtion by Lines in Vim/Evil-mode
description: A simple way to quickly navigate by chunks of lines when using a modal editor
tags: emacs vim
---

tldr:
Assume you want to quickly jump down 30 lines. You could reach to press '3' then '0' followed by 'j' <30j>. However, I prefer to hit '3', '3' then 'j' followed immediately by '3' and 'k' <33j3k>. It's 2 more keystrokes, but I can make them faster than I can reach up for '3' then '0' and get back to home row.

## Background
If you've read more than one or two posts on this blog, you know I love modal editing, starting first with vim and now using emacs with Evil-mode. To increase my speed navigating through code, my line numbering scheme shows relative numbering for all lines accept for the current line (which is the actual line of source code). This allows me to quickly determine the number of rows I am from the code I want to move to.

## Problem
If you have to move more than 9 lines of code (in either direction) you need to input two numbers before telling evil-mode which direction to go ('j' for down, 'k' to go up). I've never fully adopted touch-typing, so my hands fly all around the keyboard, but I do always find my way back to the home row. Navigating 20, 30, 40 lines is difficult for me. I have to reach for the '3' and then find the '0' and get back to the home row.

## Solution (Warning - this might be a little controversial)
Assume I want to move to code 20 lines below. What I've started doing is hitting '2', '2', 'j', '2', 'k' <22j2k>. This means I can leave my left hand on the '2' key for all these actions. Same with '1' or '3' etc. This can clearly be extended to moving to lines above your current line, just hit the necessary number twice key followed by 'k', the number once again and 'j' (example, move up 30 lines <33k3j>).

Typically, vim purists are all about using the fewest keystrokes. I embrace this (I enjoy modal editing for the efficiency of keystrokes), but for me, this saves me time.
