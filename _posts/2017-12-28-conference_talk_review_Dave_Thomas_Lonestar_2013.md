---
layout: post
title: Dave Thomas "Power of Erlang, Beauty of Ruby"
---
tldr
 - The future is functional
 - Elixir is a functional language built on top of Erlang
 - Elixir (thanks to Erlang and OTP) has already "solved" concurrency
 - [Dave's talk](http://confreaks.tv/videos/lonestarruby2013-elixir-power-of-erlang-joy-of-ruby){:target="_blank"}

*Warning to the future watcher: Unfortunately, the video sound is terrible!*
video is a little under 40 minutes.

Dave Thomas gave the talk titled "Power of Erlang, Beauty of Ruby" at the 2013 Lonestar Ruby Conference.


He loves Ruby but says 'We all must keep eye on what is going on or risk falling out of date.' So... if he's an avowed Rubyist, why talk about Elixir at Ruby conf?

Dave says he has been looking for "this" for 10 years. The 'this' is the [Elixir Programming Language](https://elixir-lang.org/){:target="_blank"}. Why has he been looking for it for a decade?

Dave believes the "Future is functional and concurrent". His rationale for this is a familiar line of reasoning:
 - Moore's law is running up against the laws of physics
 - The Intel i7 processor on his machine (as of 2013) had roughly 1 Billion transistors
 - So many processors cannot be working on same thing at the same time, so you need threading/parallelism

It's been well-established that the human mind can handle a sufficiently-complex, single-threaded programming model. Once more than one thread of execution is possible, we enter an unfamiliar realm.

So, if the way forward is not more processing power on a single chip, but parallel processing, and parallel processing is **HARD**.
Software (and functional programming) will be the way to "solve" Moore's law

Dave's Elixir introduction is:


`Elixir is Functional |> Concurrent |> Pragmattic |> Fun`

Dave gives us a very fast overview of some if the language's primitives and core semantics:
 - Describes pattern matching through `a = 1`
 - Makes the case for pattern matching
 - All compiled elixir code must go in a module (and this is how Erlang manages code)
 - Erlang's vaunted abilities for hotswapping code is done at the module level
 - He shows us how elixir code is simply a series of expressions which allows for hygenic metaprogramming (eg. it won't overwrite any local values - I think)
 - Everything has [lexical scoping](https://en.wikipedia.org/wiki/Scope_(computer_science){:target="_blank"})
 - You can see that for an untyped language, error messages are very good (even back in v 0.10.1)
 - Shows elixir comes with it's own testing framework - ExUnit
    - Show how great the ExUnit framework reports results of the test (after realizing he needs to use `==` and not `=` in ExUnit)

### Tiptoeing into the Elixir-is-a-functional-ruby holy war
Dave says elixir code looks like Ruby code if you squint.

_My thoughts_: It's true, for folks that have seen or used ruby code, you'll notice familiar syntactical elements throughout elixir; however, syntax and semantics are two different things. I come from a functional programming background, so the idiomatic way of writing elixir code is familiar; however, for folks that have been writing ruby for a while, you will probably get tripped up once or twice because the syntax is familiar, but the semantics and idioms are not. Might make the context switch a bit harder at first.

_Where DT shows what I mean_
He notes the problem of familiar syntax in an unfamiliar language is it can be hard to understand which code to write
-we see this as he is pulling together a test for his fib / map functions


Dave makes a good point: Because of elixir's functional semantics, your functions are essentially a specification for the operation you are trying to do, and he shows this with the following examples:
 - Fibonacci
 - finding List length
 - Elixir has started to change the way he programs

shows the `.` (dot) syntax necessary to call a named lambda function (which I have always cringed when seeing). Can't we find a way to get rid of this?
Actually he glosses over the 'dot' function and need for `^` ([this is called the 'pin operator'](http://elixir-lang.github.io/getting-started/pattern-matching.html#the-pin-operator)){:target="_blank"}

### Kudos to DT for live coding - great job
very nonchalant about a live coding exercise that has stalled out - takes a drink...talks with his audience...awesome stuff


Towards the end he embarks on an implementation of `pmap` (map function that can take advantage of parallel processing)


## Fun or interesting things I noticed throughout
 - When he opens up iex (the Elixir repl) you can see he's running Erlang ER16B and elixir v 0.10.1-dev
 - What is Dave Thomas's accent? I believe he is from England, but has lived in Texas for a number of years...that might explain it
 - If anyone has seen him throughout the years, his appearance seems to change significantly from time to time
 - Oddly, he makes joke that Gordon Moore (of Intel) looks like 'the Wendy's guy' - isn't the name of the founder of Wendy's Dave Thomas???
 - He's using Sublime Text (although in other places I have seen him using emacs) and also a font that has ligatures (-> looks like an arrow). but later on, there is no ligature of the arrow. strange
 - why does he call the directory BluePeter where he stored examples prepared earlier?

## Overall Impression
  - Not a bad intro by a guy that knows a thing or two about introducing a language
  - The sound is just terrible, but I'd say video is still worth watching
  - If you already know the language, you won't be exposed to anything new
