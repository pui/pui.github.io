---
layout: post
title: Delegation
---

It's been a long while since I've done any coding related blogging, so I thought I'd write about something I learned recently.

[Delegation](http://en.wikipedia.org/wiki/Delegation_\(programming\)) is one of those object-oriented programming concepts that I don't think about as much as say, inheritance or polymorphism, but it's a sensible thing that makes code cleaner.  

Last week I found out about ActiveSupport#delegate, which can be used to delegate an object's method to another object's method.  Here's a simple example:

I have coworkers with severe allergies.  We're going to assume that a coworker has one severe allergy for my simple example.  This seems to be true so far, no one I've worked with has had more than one, send them to the emergency room, allergies. 

Here's the two classes, with Coworker wanting to delegate the instance method severe_allergy_description to SevereAllergy: 

    class SevereAllergy < ActiveRecord::Base
      def description
        "The reaction to #{name} is #{reaction}."
      end

    class Coworker ActiveRecord::Base
      has_one :severe_allergy
  
      def severe_allergy_description
        severe_allergy.description
      end
    end

I've seen the above pattern a lot. Instead we could do this: 

    class Coworker ActiveRecord::Base
      has_one :severe_allergy

      delegate :description :to => :severe_allergy, :prefix => true
    end

Let's use it:

    coworker = Coworker.create(:name => "CK")

    coworker.create_severe_allergy(:name => "cats", :reaction => "death")
    coworker.severe_allergy_description # => "The reaction to cats is death."

I'm pretty surprised I haven't seen this used before, seeing as it's been around since Rails 2.2.  
  
Next up, I hope to make the blog prettier to improve my sad css skills, master javascript, familiarize myself with jQuery and make more [cookies](http://twitter.com/pm/status/10298416867) at work. 