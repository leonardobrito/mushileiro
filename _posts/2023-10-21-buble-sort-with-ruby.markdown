---
layout: post
title:  "Bubble sort algorithm with ruby"
date:   2023-10-21 12:24:00 -0300
categories: ruby algorithms
---
A simple ruby sorting algorithm that repeatedly steps through the list, campares adjacent elements, and swaps them if they are in the wrong order.

{% highlight ruby %}
def bubble_sort(list)
  list_size = list.size

  (0...list_size).each do |item|
    for position in 0...(list_size - item - 1)
      if (list[position] > list[position + 1])
        # swap
        temp = list[position]
        list[position] = list[position + 1]
        list[position + 1] = temp
      end
    end
  end

  list
end

list = [100, 2, 3, 4, 5, 7, 1, 2]

print bubble_sort(list)
#=> [1, 2, 2, 3, 4, 5, 7, 100]
{% endhighlight %}
