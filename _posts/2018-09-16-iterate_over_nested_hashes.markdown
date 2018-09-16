---
layout: post
title:      "iterate over nested hashes"
date:       2018-09-16 19:12:36 +0000
permalink:  iterate_over_nested_hashes
---


So for some reason I find iterating over hashes much easier than arrays. Not sure if it's because hashes have keys: values so it's much easier for me to break it down or just that I have come this far into the course (not that far).

So the next code that I got stuck on was the lab that has "All supplies in holidays" where we have to list the holidays and supplies in certain format and capitalize the name of the holidays. This was an interesting method that I had to write. I definitely have the right idea but it took me a while to finally figure out the final code. I still feel like there is a much easier way to do it... 

First the hash given:

```
given that holiday_hash looks like this:
   {
     :winter => {
       :christmas => ["Lights", "Wreath"],
       :new_years => ["Party Hats"]
     },
     :summer => {
       :fourth_of_july => ["Fireworks", "BBQ"]
     },
     :fall => {
       :thanksgiving => ["Turkey"]
     },
     :spring => {
       :memorial_day => ["BBQ"]
     }
   }
```

Here's what I came up with to print the info in the hash out to the form:
Season:
      Holiday: Supplies
			

```
def all_supplies_in_holidays(holiday_hash)
  holiday_hash.each do |seasons, holidays_in_season|
    puts "#{seasons}:".to_s.capitalize!
    holidays_in_season.each do |holiday, supplies|
      if holiday.to_s.split("_").size > 1
        holiday = holiday.to_s.split("_").each {|word| word.capitalize!}
        puts "  #{holiday.join(" ")}: #{supplies.join(", ")}"
      else
        puts "  #{holiday.capitalize}: #{supplies.join(", ")}"
      end
    end
  end
end

```

First, iterates over the first level and prints "Season:" (that was easy)

Next, the #holidays_in_season that need to be separated under holiday and supplies. So the supplies isn't hard because the supplies are already capitalized and listed in strings in an array, so I didn't have to do much other than converting them from an array into string. 

The names of the holidays are the toughest because there are a few things that needed to be done before it will print it correctly. It needs to be converted to strings, have no underscore between the words, capitalize each word, then display as 1 single string if there is more than 1 word for the holiday, ie: New Years. 

The code in short: if the size of the #holiday string is more than 1, then #to_s, #split, #.each, #capitalize! each word and assign it as the value of #holiday (which results in an array). Then print #holiday with #.join so that the words are back from an array to a string.

