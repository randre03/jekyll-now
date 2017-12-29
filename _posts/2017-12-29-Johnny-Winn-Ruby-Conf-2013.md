---
layout: post
title: Johnny Winn "Polyglot in the Code An Elixir/Ruby Mashup"
description: A review of Johnny Winn's "Polyglot in the Code; An Elixir/Ruby Mashup", given at Ruby Conf 2013
tags: conference elixir ruby
---

tldr
 - This talk is a bit dated, but the lessons about using what you already know to learn something you want to know are timeless
 - Johnny does a good job walking through a large swath of the elixir universe as of 2013 in a short amount of time
 - Johnny's talk can be found [here](https://confreaks.tv/videos/rubyconf2013-the-polyglot-in-the-code-an-elixir-ruby-mashup){:target="_blank"}

Video is just over 32 minutes long.

## YAETAARC (Yet Another Elixir Talk At A Ruby Conference)

***Side note:***

*Recall, 2013, was early days for elixir. Some of the tooling and libraries we now take for granted were not yet avaialble. This was also the time in elixir's development when elixir users were evangelizing the language to prediminately ruby users. You can see this in Dave Thomas's talk to Lonestar Ruby in 2013 (see my review [here]({% post_url 2017-12-28-conference_talk_review_Dave_Thomas_Lonestar_2013 %}){:target="blank"}).*

[Johnny Winn](https://twitter.com/johnny_rugger){:target="_blank"}, co-host of the venerable [Elixir Fountain podcast](https://www.patreon.com/elixirfountain){:target="_blank"} (his co-host is [Sean Callan](https://twitter.com/doomspork){:target="_blank"}) presents to a group of ruby coders how he has used the best of elixir and the best of ruby to meet his needs.


Johnny and his wife have a lot of experience with education and how people learn. He starts the talk with some of these concepts. Such as:
 - [Constructivism](https://en.wikipedia.org/wiki/Constructivist_teaching_methods){:target="_blank"}; and
 - [Scaffolding](https://en.wikipedia.org/wiki/Instructional_scaffolding){:target="_blank"}.


So why are they valuable? And why is he sharing these things?
 - JW says most of us come to programming to learn and to be challenged.
 - But we need direction.
 - Johnny gives us the following quote:
 > "Efforts and courage are not enough without purpose and direction."
 > -[John F. Kennedy](https://en.wikipedia.org/wiki/John_F._Kennedy){:target="_blank"}

### The Analogy
His kids would experiment by cooking (which my kids sort of do)..they would work and not have any idea of what they were doing, _but they would not get frustrated_.

**The Lesson**: We can take advantage of learning by finding something we’re interested in, something we like.

Knowledge is constructed, not acquired - so we can build up our knowledge
We learn by building on existing knowledge (see 'scaffolding')

*(Reviewer's Note: This is all well and good, but when are we getting to the code???)*

Right on cue, Johnny asks the rhetorical question: what does all this have to do with programming and being polyglot?


The point is we can use knowledge of one language...to learn another!
- On the CodeNewbie podcast it was once said:
> Learning your first language is hard, learning the second language is harder, and then all others are easier.
 > - I think it was [Mary L Gordon](https://www.codenewbie.org/podcast/learning-to-code-in-the-1960s){:target="_blank"}. Great talk by the way.


Side note: if you'd like to learn about how browsers work, CodeNewbie's interview with [Lin Clark](https://www.codenewbie.org/podcast/how-do-browsers-work){:target="_blank"} was *AMAZING*.


## Back to the talk
Johnny says he'll teach us some elixir code and add a touch of ruby to fill in the gaps we don’t know about elixir. (recall the statement above - this was early days).

Great Point: Elixir and Erlang share data types so no performance cost when calling one from the other!

#### *Please Note: The following section headings correspond to the sections of the talk as Johnny lays them out:*


## Put the Fun in Function
*(This section is about the great 'mix' build tool)*
 - Plays a recorded coding demo
 - Mentions the 'Dot' when calling an anonymous function (I still hate this thing)
 - All elixir code must be in module
 - Elixir has a repl called [iex](https://hexdocs.pm/iex/IEx.html){:target="_blank"}
 - Most everything is inside a “do” block which is a macro
 - *Reviewer's Note: Johnny seems to be spending time waiting for his recording to catch-up to where he is*
 - Moves on to pattern matching (apparently, at the conference Dave Thomas already overviewed this so he leaves that to him)
 - Shows that you can convert from pattern matching in the function args to a guard clause (nice touch)
 - Recursion

## Throw in a Mix
*(This section is about the great 'mix' build tool)*
 - Similar to [leiningen](https://leiningen.org/){:target="_blank"} for clojure
 - Allows us to know if we’re in dev/test/prod environment
 - This is so early that the web framework he discusses is [Dynamo](https://github.com/dynamo/dynamo){:target="_blank"} as this was befored [Phoenix](http://phoenixframework.org/){:target="_blank"}.
    - Also mentions an elixir MVC framework called [Weber](http://elixir-web.github.io/weber/){:target="_blank"}.

## Remember the Ecto
*(This section is about the elixir mdoule [Ecto](https://github.com/elixir-ecto/ecto){:target="_blank"} which may or may not be an [ORM](https://en.wikipedia.org/wiki/Object-relational_mapping){:target="_blank"})*
 - Ecto handles databaseinteraction
 - Has the concepts of:
   - Repo,
   - Entity,
   - Queries.

## What is missing?
*(This section is where Johnny points out the functionality that as of 2013 he could not get from elixir as a means to segue to combining with ruby)*

 - Johnny says [ExUnit](https://hexdocs.pm/ex_unit/ExUnit.html){:target="_blank"} (the elixir testing framework) does not help with [Behavior Driven Development](https://dannorth.net/introducing-bdd/){:target="_blank"} - which he uses at HashRocket
 - And at the time of this talk Ecto did not handle database migrations

So, let’s throw in a touch of Ruby to fill in these gaps ...for the things you’re missing, just inject Ruby into your elixir project (says it is easy)
 - *Reviewer's Note: at this point in the talk, I start to think that much of what is proposed in this talk was out of necessity in 2013 and no longer necessary to bring in ruby to address these items as elixir now has the necessary library modules.*

Johnny creates a Gemfile and adds to the mix project to bundle cucumber, selenium, capybara and rspec

How do we do data migrations (remember Ecto didn’t do this back then)
- Adds Builders active_record and pg (Postgres)
- Uses rakefile to perform the migration(s)

After getting ruby integrated, now is time for elixir
 - *Reviewer Question: What is the delineator between what he’s using ruby for and elixir for?*
 - Sets up Ecto for managing the model (while using ruby to do the migrations)
 - Dynamo Router: JW notes anyone that has used Sinatra should be familiar with this

## Wrapping Up
 - Seems to be having som issues with the display of the presentation, but not too distracting
 - Runs `mix test`, ruby is running the test database, then cleans up and ruby gets out of the way
 - Circles back around to the beginning and how we can use constructivism (use what we already know eg. Ruby) to build on what we want to know (elixir).


### Kudos to Johnny
Johnny does a good job of showing us a real process for integrating ruby into elixir. He does not hide the errors from us, and addresses when things don’t work, and testing


## Fun or interesting things I noticed throughout
 - Johnny has 7, homeschooled kids!
 - Seems to be spending time waiting for his recording to catch-up to where he is
 - Appears Johnny is using vim (what theme is that? Seriously, if you know please let me know!)
 - JW notes Dynamo was still in flux then, so things could change (they sure did)
 - His presentation template is clearly indicative of who Johnny is (I like to think if have some sense of this after having listened to his podcast so many times)
   - There are some cool leaves, that look like waves at bottom of slides and any square outlines are actually not “square”, they are more like rhombuses.
 - JW has been developing for better part of 15 yrs, really likes ruby and how you can use it with other languages.

## Overall Impression
 - I personally like Johnny (have never met him or spoken to him directly, but seems like a very cool dude)
 - Watching this talk post 2013/2014 it begins to show its age, however:
 - I think the ability to leverage what you already know to either (i) learn something new, or (ii) fill in the gaps of a new technology is a skill worth knowing and developing.
