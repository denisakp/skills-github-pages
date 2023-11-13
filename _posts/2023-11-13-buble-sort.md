---
title: "Bubble Sort Unveiled: Sorting Simplified with Python"
date: 2023-11-13
description: "Dive into the fundamentals of the bubble sort algorithm in Python and unravel a straightforward approach to sorting. This post guides you through the inner workings of bubble sort, showcases hands-on code examples, and highlights its strengths and limitations for practical use"
---

# Introduction

Sorting is a fundamental operation in computer science, and there are various algorithms to accomplish this task.
One of the simplest sorting algorithms is the Bubble Sort. While not the most efficient for large datasets,
understanding Bubble Sort can be a great way to grasp the basic principles of sorting algorithms. In this post,
we'll explore what Bubble Sort is and how to implement it in Python.

# What is Bubble sort

Bubble Sort is a comparison-based sorting algorithm that repeatedly steps through the list to be sorted. 
It compares adjacent elements and swaps them if they are in the wrong order. The algorithm continues iterating through the
list until no more swaps are needed, indicating that the list is now sorted.
The main idea behind Bubble Sort is that larger elements "bubble up" to the end of the list, while smaller elements 
"sink" to the beginning.

# How Bubble Sort Works

Bubble Sort is a simple sorting algorithm that works by repeatedly stepping through a list of elements (like numbers or words),
comparing each pair of adjacent items, and swapping them if they're in the wrong order. The pass through the list is repeated for
as many times as there are elements in the list. The algorithm gets its name because the smaller elements "bubble" to the top of the list
like air bubbles in water, while the larger elements "sink" to the bottom.

Let's break this into more understandable words

1. **Comparison and swapping**

   The algorithm starts by comparing the first two elements in the list. If the first element is greater than the second, it swaps them. This process continues for every adjacent pair of elements in the list.

2. One pass through the list
   
   - After this first pass through the list, the largest element has bubbled up to the last position.
   - The algorithm then performs the same comparison and swapping process for the remaining elements in the list, excluding the last one.

3. **Repeat until sorted**
   
   - The algorithm keeps repeating these passes through the list until no more swaps are needed. This means that all elements are in their correct sorted positions.
   - During each pass, smaller elements "bubble up" to their appropriate positions.

4. **Optimization**
   
   A small optimization can be applied by introducing a flag that keeps track of whether any swaps were made during a pass. If no swaps were made, it means the list is already sorted, and the algorithm can stop early.

5. **Time Complexity**
   - In the worst case, Bubble Sort requires n passes through the list, where n is the number of elements. For each pass, it compares and possibly swaps adjacent elements.
   - This results in a time complexity of O(n^2), which means the algorithm's performance becomes slow for large lists.

In summary, while Bubble Sort is conceptually simple and easy to understand, it's not very efficient for large datasets due to its quadratic time complexity.
It's mainly used for educational purposes and understanding sorting concepts. For practical applications,
more advanced sorting algorithms like Quick Sort, Merge Sort, or built-in sorting functions in programming languages are preferred due to their better performance.

# Implementation using Python

Here's a simple step-by-step implementation of the Bubble Sort algorithm in Python 3 (Flagged Optimized Bubble Sort) which involves using a flag to determine whether any
swaps were made during an iteration. If no swaps are made, the algorithm knows that the array is already sorted and can terminate early.

``` python [buble_sorting.py]
from typing import List, Any

def bubble_sort(collection: List[Any]) -> List[Any]:
    n = len(collection)

    for i in range(n):
        swapped = False  # Initialize the flag
        for j in range(0, n-i-1):
            if collection[j] > collection[j+1]:
                collection[j], collection[j+1] = collection[j+1], collection[j]  # Swap the elements
                swapped = True
        if not swapped:
            break  # No swaps were made, collection is sorted

    return collection

def main():
    # Input collection from the user
    input_str = input("Enter a collection separated by a comma:")
    input_list = [x.strip() for x in input_str.split(',')]

    # Print sorted collection
    print(*bubble_sort(input_list), sep=",")

if __name__ == "__main__":
    main()
```

# Conclusion

Bubble Sort is a basic sorting algorithm that serves as a foundation for understanding more complex sorting methods.
While it's not the most efficient algorithm for large datasets, it's a great starting point to learn about the principles of 
sorting and algorithm optimization. As you delve further into the world of computer science, you'll encounter more advanced
sorting algorithms that offer better performance.
Remember, understanding Bubble Sort is like learning to ride a bicycle before moving on to a motorbike. It equips you with 
valuable insights into sorting techniques that will be useful when exploring more sophisticated algorithms.

