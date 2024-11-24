---
layout: post
title:  "Quick sort algorithm with ruby"
date:   2024-11-23 22:49:00 -0300
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

  for idx in 1...list_size
    list[idx] < pivot ? left << list[idx] : right << list[idx]
  end

  [*quick_sort(left), pivot, *quick_sort(right)]
end

list = [100, 2, 3, 4, 5, 7, 1, 2]

print quick_sort(list)
#=> [1, 2, 2, 3, 4, 5, 7, 100]
{% endhighlight %}

#### Complexity
- Time:
  - Best Case: (Ω(n log n)): The pivot element divides the array into two equal halves.
  - Average Case (θ(n log n)): The pivot divides the array into two parts, but not necessarily equal.
  - Worst Case: (O(n²)): The smallest or largest element is always chosen as the pivot (e.g., sorted arrays)
- Space: O(n) due to recursive call stack

#### Advantages
- Divide-and-conquer algorithm;
- Efficient on large data sets;
- Low overhead, requires a small amount of memory to function;

#### Disadvantages
- Worst-case time complexity of O(n2);
- Not a good choice for small data set;
- Not a stable sort, if two elements have the same key, their relative order will not be preserved
