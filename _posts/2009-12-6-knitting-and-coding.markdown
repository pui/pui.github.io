---
layout: post
title: Coding and Knitting
---

I spent Saturday working on my completely useless gem, [henrietta_pussycat](http://github.com/pui/henrietta_pussycat).  I hadn't looked at it in a long time, so there was a bit of "um, what was I doing?" that I cleaned up.  I also added [jeweler](http://github.com/technicalpickles/jeweler).  I'm happy when I can find ways to avoid dealing with configuration.  

There's a method in henrietta_pussycat called classic_meow_insert.  This method should replace all words with "meow" except for the words beautiful, telephone and Mr. Rogers.  Replacing everything but beautiful and telephone is easy, not replacing Mr. Rogers is not, since it is really two words.  I have yet to come up with a good solution to do this, but I did learn about regular expressions' negative/positive look-behind and look-ahead.  I spent a long time thinking that there must be some magical regular expression that would allow me to replace everything but the words I wanted, but then I realized I was trying to use a regular expression to *not* match something.  That's not what regular expressions are for!  So, I'm still stuck, but I've decided that I can't solve this problem, or at least not completely, with one regular expression.  

henrietta_pussycat is on [gemcutter](http://gemcutter.org/gems/henrietta_pussycat) and as of me writing this, 13 people have downloaded it.  That is crazy.  

As for knitting, somehow I'm almost half-way done [my so called scarf](http://www.sheepinthecity.prettyposies.com/archives/000079.html).  It's the only holiday-ish gift I'm making this year and I'm pretty happy with it thus far.  Next up, (after I finish the February Lady sweater) another [shrug](http://yarnbearer.wordpress.com/2009/08/17/gaia/)

