---
layout: post
title: inject vs. each_with_object
---

I [tweeted](http://twitter.com/erica_now_knows/status/5323399139) about this a while back, but I thought I'd write about how I ran into problems with inject and how each_with_inject made it all better.  

So I was originally using inject to create a hash of video game data from an array of div elements I was parsing with hpricot like so:  

    div_elements.inject({}) do |hash, div_element|
        game_name = div_element.at("//p/a").inner_text
        last_played_online_time = div_element.at("//p/strong").inner_text
        hash[game_name] = last_played_online_time
        hash
    end

But sometimes, a user had never played a game online, so the text in the strong element I was checking for the time would contain something like "not played" in this case.  I thought I could easily solve this by doing:   

    div_elements.inject({}) do |hash, div_element|
        game_name = div_element.at("//p/a").inner_text
        last_played_online_time = div_element.at("//p/strong").inner_text
        next if last_played_online_time =~ /not played/i
        hash[game_name] = last_played_online_time
        hash
    end

But this was bad.  Next would return nil, setting the accumulator to nil and causing bad errors on the next pass through the block.  each_with_object did not have this problem.  Changing things to use it looked like:  

    div_elements.each_with_object({}) do |div_element, hash|
        game_name = div_element.at("//p/a").inner_text
        last_played_online_time = div_element.at("//p/strong").inner_text
        next if last_played_online_time =~ /not played/i
        hash[game_name] = last_played_online_time
    end

So not that different!  But better.  I didn't have to worry about returning the accumulator, making things a little simpler.
  