---
layout: post
title: Binary search algorithm with ruby
date: 2023-10-26 20:05 -0300
categories: ruby algorithms
---

An efficient search algorithm in ruby that finds the position of a target value within a sorted array.

{% highlight ruby %}
def midFromLowHigh(low, high)
  ((low + high) / 2).floor
end

def binary_search(list, target)
  low = 0
  high = (list.size - 1)

  begin
    mid = midFromLowHigh(low, high)
    guess = list[mid]

    if (guess === target); return mid
    elsif (guess > target); high = mid - 1
    else low = mid + 1 end
  end while low <= high

  return -1;
end

list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]

p1 = binary_search(list, 15)
puts "position #{p1} value #{list[p1]}"
#=> position 14 value 15

p2 = binary_search(list, 1)
puts "position #{p2} value #{list[p2]}"
#=> position 0 value 1

p3 = binary_search(list, 9)
puts "position #{p3} value #{list[p3]}"
#=> position 8 value 9

p4 = binary_search(list, 20)
puts "position #{p4} value #{list[p4]}"
#=> position -1 value 15
{% endhighlight %}
