---
layout: post
title: Fibonacci algorithm with ruby
date: 2023-11-11 10:57 -0300
categories: ruby algorithms
---

A series of numbers where each number is the sum of the two preceding ones, often used as an example for dynamic programming.

{% highlight ruby %}
def fibonacci(value)
  fib = [0, 1]

  (2..(value)).each do |value_idx|
    fib[value_idx] = fib[value_idx - 1] + fib[value_idx - 2]
  end

  fib[value]
end

puts  fibonacci(7)
#=> 13
{% endhighlight %}
