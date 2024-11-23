---
layout: post
title:  "Bubble sort algorithm with ruby"
date:   2024-11-23 13:12:00 -0300
categories: ruby algorithms
---
A simple ruby sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.

{% highlight ruby %}
def bubble_sort(list)
  list_size = list.size

  (0...list_size).each do |element|
    for idx in 0...(list_size - element - 1)
      if (list[idx] > list[idx + 1])
        # swap
        temp = list[idx]
        list[idx] = list[idx + 1]
        list[idx + 1] = temp
      end
    end
  end

  list
end

list = [100, 2, 3, 4, 5, 7, 1, 2]

print bubble_sort(list)
#=> [1, 2, 2, 3, 4, 5, 7, 100]
{% endhighlight %}

#### Complexity
- Time: O(n2)
- Space: O(1)

#### Advantages
- Easy to understand;
- Not require additional memory space.

#### Disadvantages
- Time complexity of O(n2) that's is slow for large data sets;
- Requires a comparison operator to determine the relative order of the elements in the input data set.
