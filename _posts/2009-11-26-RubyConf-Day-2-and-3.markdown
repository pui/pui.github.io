---
layout: post
title: RubyConf day 2 and 3
---

I was exhausted by the end of the conference, but there were many more interesting talks that made the travel and tiredness worth it.  I really enjoyed the [Python](http://www.python.org/) and [Rubinius](http://rubini.us/) talks.  I might start dabbling with some Python even.  Also, [Aaron Patterson](http://tenderlovemaking.com/) and [Ryan Davis's](http://blog.zenspider.com/) talk was pretty amazing.  I think if I ever write PHP again, it will be with [Phuby](http://github.com/tenderlove/phuby).  

So a concept that came up in a lot of talks was domain specific languages.  I'd never heard of them before, so I asked [Chris](http://www.shiftcommathree.com/) to give me a short explanation, which he did, but I figured I needed to read up on this myself.  I really liked an analogy used in the [Wikipedia article](http://en.wikipedia.org/wiki/Domain-specific_language) on domain specific languages: "A domain-specific language is like an electric drill: it is a powerful tool with a wide variety of uses, but a specific context, namely, putting holes in things (although it might also be used to mix paint or remove screws)."  As opposed to a general purpose language, such a Ruby, C, or what have you, which can be used to do whatever you like.

I went looking for a concrete example and found Martin Fowler's [writeup](http://martinfowler.com/dslwip/Intro.html) which helped make even more sense of things.  One of the examples Martin Fowler gives is creating a finite state machine in Ruby (I always thought these were fun to draw).  The finite state machine would be considered an internal domain specific language because it is Ruby, but with a very limited scope.  An external domain specific language would be something like YAML in a rails app, since YAML is a different language, and all it does is serialize data.  

The concept of a domain specific language isn't limited to software development (so says [Wikipedia](http://en.wikipedia.org/wiki/Domain-specific_language#Overview)) and it occurred to me that knitting terms and abbreviations could be considered a domain specific language.  I thought this was nifty.  
