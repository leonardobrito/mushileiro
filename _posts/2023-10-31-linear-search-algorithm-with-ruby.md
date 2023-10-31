---
layout: post
title: Linear search algorithm with ruby
date: 2023-10-31 20:19 -0300
categories: ruby algorithms
---

A simple search algorithm in ruby that finds the position of a target value within a list

{% highlight ruby %}
def linear_search(arr, target)

  arr.each_with_index do |_, index|
    if arr[index] == target
      return index
    end
  end

  return -1
end

list = [100, 2, 3, 4, 5, 7, 1, 2]

puts "Index: #{linear_search(list, 5)}, value: #{list[linear_search(list, 5)]}"
#=> Index: 4, value: 5
puts  linear_search(list, 101)
#=> -1
{% endhighlight %}
