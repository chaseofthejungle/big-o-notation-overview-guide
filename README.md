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
  + **O(log n)** (or 'logarithmic')
  + **O(n)** (or 'linear')
  + **O(n log n)** (or 'linearithmic')
  + **O(n²)** (or 'quadratic')
  + **O(2ⁿ)** (or 'exponential')
* Big O reflects growth rate rather than actualized speed. *It does not offer data about an algorithm's actual runtime*.
  + Big O is a mathematical mechanism for measuring algorithmic scalability for worst-case behavior scenarios (input level associated with maximal processor burden).
  + Consequently: tests of input data and individual data structures still need to be performed.

<hr />

## 2. <a name="supplemental">Supplemental Resources</a>

* *[Java Data Structure Leetcode Interview Questions](https://github.com/chaseofthejungle/java-data-structure-leetcode-interview-questions)*
* *[Java Quick Reference Guide](https://github.com/chaseofthejungle/java-quick-reference-guide)*
* *[Intro to the Java Collections Framework](https://github.com/chaseofthejungle/intro-to-java-collections-framework)*
