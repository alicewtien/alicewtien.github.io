---
layout: post
title:      "true or false: 8 + 9 == 10 || true == (false && true)"
date:       2018-07-15 17:48:54 +0000
permalink:  true_or_false_8_9_10_true_false_and_and_true
---

Booleans... true or false, simple, right? Nope.

It all depends on how it's written. Two statements of true and false can be equal to true or false.

I sure was confused when I was trying to write code with booleans in them. When it's plain English, it's definitely much simpler. Double negative equals position and that's it. I played around IRB to see how Ruby would determine the elements (or statements) to be truthy or falsey. 

I learned that for a statement to return the desired value of true or false, I need to evaluate every single element of the statement separately and then put them back together. Booleans are definitely fun and very interesting!
