---
layout: post
title:      "now serving... "
date:       2018-09-02 22:03:58 +0000
permalink:  now_serving
---


As I continue through Procedural Ruby, the most difficult lab was the Deli Counter lab.  I kept trying to write 1 method to do multiple different things thinking it will be able to mimic what I do at work.

When I'm at work, I can be on the phone listening to a patient talking about his/her problem, typing up a new prescription, and waving at my tech to tell the patient at the window that his medication requires prior authorization, all at the same time.

This definitely was a difficult lab for me. 

The first part: show everyone's place in line - I was trying to write the method without having to create an array for it but it was not working. After researching, it seems the simplest way IS to create an array, add exactly what you want into an array, then convert it to a string.

```
#line method: shows everyone's current place in line

def line(the_deli)
  the_line = []
  if the_deli != []
    the_deli.each_with_index { |name, index|
      the_line << "#{index+1}. #{name}" }     *#make the array the way you want the texts to display*
      puts "The line is currently: #{the_line.join(" ")}"   *#convert into string*
  else
    puts "The line is currently empty."
  end
end
```

The second part: take a number - add the names into the array #the_deli then #puts the #name and by using the #.length method to tell the person exactly what place are they in the array. The #.length always starts the count at 1.

```
#take a number: gives "name" a "number" in line
def take_a_number(the_deli, name)
  the_deli << "#{name}"     *  #names to be added into the_deli array*
  puts "Welcome, #{name}. You are number #{the_deli.length} in line."
end
```

And last but not least: Now Serving (this always brings back the unpleasant memories in DMV... ). I find it the easiest to loop through until the line is 0. As long as the #.length of #the_deli is greater than 0, it will continue to show now serving #name in line.

```
#now serving
def now_serving(the_deli)
  if the_deli.length > 0
    puts "Currently serving #{the_deli[0]}."
    the_deli.shift   * #use .shift to remove 1st item in the array*
  else
    puts "There is nobody waiting to be served!"
  end
end
```


Side note...
As I continue through the course, I really want to spend more time and focus more on the course. However, with my currently functioning as the pharmacy manager while waiting for the new manager to arrive, I find myself working 50-60 hours a week and spending less time on my course. I think it is time to talk to the boss about cutting back hours at the pharmacy so I can focus more on programming/coding...
