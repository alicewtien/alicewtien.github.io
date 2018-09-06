---
layout: post
title:      "and this is the PRIME..."
date:       2018-09-06 19:04:12 +0000
permalink:  and_this_is_the_prime
---


What's a prime number? It's a number that's only divisible by itself & the number 1 and is greater than 1. That's been an easy concept for me for as long as I remember (from the time I learned about prime numbers).

However, to write a method to determine if a number is a prime number wasn't as easy as it was for me to understand. My method has 3 parts:

1. The number has to be greater than 1.
2. The number CANNOT be divisible by the numbers 2 through 1 less than then number.
3. The number 2 is the only exception to rule #2.

I thought I would be able to write the method in 5 minutes but it didn't work. It literally took me hours to try to put that explanation of prime numbers into a method.

I tried different ways to write the method but it either returned 4 as a prime number, asked me to not forget to take into account of negative numbers, or the number 1763 kept showing up as a prime number when it's not...

When it finally worked, I realize that it helped me very much to actually write the pseudo code first. Up to this point I have always conceptualize it in my head first then just write the code. Little did I know that writing the code out or just having the concept written out would help me figure the code. I also noticed that if I didn't put the statement where it eliminates any number < or = 1, it will fail and tells me that I need to take into account the negative numbers.

```
def prime?(n)
  if n <= 1
    false
  elsif n == 2
    true
  else (2..n-1).none? { |x| n % x == 0 }
  end
end
```

So, the first part: any number  #n  that is not greater than 1, false. 
The second part, the exception of the number 2. 
After the number gone through the first 2 parts and has not met any conditions to return a true/false statement, it goes through the third part.

In the last part, I have #(2..number-1) to represent all the numbers between 2 and up to the number-1 then iterate over those numbers with #none and use #|x| as the variable for those number (because x is always the variable in algebra).
So.. if none of the remainder of number divided x is zero, then it is a prime number.
