# Big O Notation Overview Guide

TODO: A brief introduction to Big O Notation and its indications for data structures and algorithms.

#### Table of Contents

1. [Algorithmic Implications](#algorithmic)
2. [Supplemental Resources](#supplemental)

<hr />

## 1. <a name="algorithmic">Algorithmic Implications</a>

* We use Big O notation to learn which data structures and their associated algorithms should lead to improved performance. 
  + Big O notation provides algorithmic efficiency implications. It reflects the upper bounds of algorithms' growth rates.
    - The notation of Big O accounts for increases in input size, reflected as 'n' values.
    - Two dimensions are directly impacted: data operations ('time complexity') and memory/space ('space complexity').
* From best to worst performance (note that individual algorithms have best, worst, and average cases), the popular Big O complexities include:
  + **O(1)** (or 'constant')
    - This means that the execution time of the algorithm stays constant, no matter the input size (the 'n' value).
      + A practical example if *O(1)*: when accessing array elements by index, execution would remain the same.
  + **O(log n)** (or 'logarithmic')
    - This means that the execution time would grow logarithmically along with the input size (the 'n' value).
      + A number's logarithm is the exponent that another value (a fixed base value) must be raised by to produce that particular number.
      + *O(log n)* is common in algorithms that repetitively divide a problem's size by half (e.g., a binary search on a sorted array).
  + **O(n)** (or 'linear')
    - This means that execution time grows linearly along with the input size (the 'n' value).
      + For example, if an 'n' value doubles, then execution time (approximately) also doubles.
      + Linear searches through non-sorted arrays have *O(n)*.
  + **O(n log n)** (or 'linearithmic')
    - This means that execution time grows in terms of 'n' times the logarithm (see the *O(log n)* explanation for a definition of 'logarithm') of the input size (the 'n' value).
      + *O(n log n)* is common in efficiency sorting algorithms (e.g., quick sort, merge sort). 
  + **O(n²)** (or 'quadratic')
    - This means that execution time grows quadratically along with the input size (the 'n' value).
      + For example, if an 'n' value doubles, then execution time (approximately) quadruples.
      + *O(n²)* is a common consequence of nested loops that iterate over their input (e.g., bubble sort and other simple sorting algorithms).
  + **O(2ⁿ)** (or 'exponential')
    - This means that execution time doubles with every linear increase in an input size (the 'n' value).
    - This is a *very* fast growth rate, and is common in algorithms that investigate all possible combinations/subsets.
      + Consequently, this leads to poor performance for larger input burdens. 
* Big O reflects growth rate rather than actualized speed. *It does not offer data about an algorithm's actual runtime*.
  + Big O is a mathematical mechanism for measuring algorithmic scalability for worst-case behavior scenarios (input level associated with maximal processor burden).
  + Consequently: tests of input data and individual data structures still need to be performed.

<hr />

## 2. <a name="supplemental">Supplemental Resources</a>

* *[Java Data Structure Leetcode Interview Questions](https://github.com/chaseofthejungle/java-data-structure-leetcode-interview-questions)*
* *[Java Quick Reference Guide](https://github.com/chaseofthejungle/java-quick-reference-guide)*
* *[Intro to the Java Collections Framework](https://github.com/chaseofthejungle/intro-to-java-collections-framework)*
