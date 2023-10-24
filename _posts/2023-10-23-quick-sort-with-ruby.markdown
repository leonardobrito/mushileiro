---
layout: post
title:  "Quick sort algorithm with ruby"
date:   2023-10-23 21:39:00 -0300
categories: ruby algorithms
---

A fast sorting algorithm that uses a divide-and-conquer strategy to sort elements, ruby version.

{% highlight ruby %}
def quick_sort(list)
  list_size = list.size

  return list unless list_size > 1

  pivot = list.first
  left = []
  right = []

  for position in 1...list_size
    list[position] < pivot ? left << list[position] : right << list[position]
  end

  return quick_sort(left).concat([pivot], quick_sort(right))
end

list = [100, 2, 3, 4, 5, 7, 1, 2]

print quick_sort(list)
#=> [1, 2, 2, 3, 4, 5, 7, 100]
{% endhighlight %}
