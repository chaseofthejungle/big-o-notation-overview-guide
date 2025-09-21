# Big O Notation Overview Guide

#### Table of Contents

1. [Algorithmic Implications](#algorithmic)
2. [Code Examples](#examples)
3. [Summary Table of Code Examples](#summary)
4. [Supplemental Resources](#supplemental)

<hr />

## 1. <a name="algorithmic">Algorithmic Implications</a>

* We use Big O notation to learn which data structures and their associated algorithms should lead to improved performance. 
  + Big O notation provides algorithmic efficiency implications. It reflects the upper bounds of algorithms' growth rates.
    - The notation of Big O accounts for increases in input size, reflected as 'n' values.
    - Two dimensions are directly impacted: data operations ('time complexity') and memory/space ('space complexity').
* From best to worst performance (note that individual algorithms have best, worst, and average cases), the popular Big O complexities include:
  + **O(1)** (or 'constant' time)
    - This means that the execution time of the algorithm stays constant, no matter the input size (the 'n' value).
      + A practical example if *O(1)*: when accessing array elements by index, execution would remain the same.
  + **O(log n)** (or 'logarithmic' time)
    - This means that the execution time would grow logarithmically along with the input size (the 'n' value).
      + A number's logarithm is the exponent that another value (a fixed base value) must be raised by to produce that particular number.
      + *O(log n)* is common in algorithms that repetitively divide a problem's size by half (e.g., a binary search on a sorted array).
  + **O(n)** (or 'linear' time)
    - This means that execution time grows linearly along with the input size (the 'n' value).
      + For example, if an 'n' value doubles, then execution time (approximately) also doubles.
      + Linear searches through non-sorted arrays have *O(n)*.
  + **O(n log n)** (or 'linearithmic' time)
    - This means that execution time grows in terms of 'n' times the logarithm (see the *O(log n)* explanation for a definition of 'logarithm') of the input size (the 'n' value).
      + *O(n log n)* is common in efficiency sorting algorithms (e.g., quick sort, merge sort). 
  + **O(n²)** (or 'quadratic' time)
    - This means that execution time grows quadratically along with the input size (the 'n' value).
      + For example, if an 'n' value doubles, then execution time (approximately) quadruples.
      + *O(n²)* is a common consequence of nested loops that iterate over their input (e.g., bubble sort and other simple sorting algorithms).
  + **O(2ⁿ)** (or 'exponential' time)
    - This means that execution time doubles with every linear increase in an input size (the 'n' value).
    - This is a *very* fast growth rate, and is common in algorithms that investigate all possible combinations/subsets.
      + Consequently, this leads to poor performance for larger input burdens. 
* Big O reflects growth rate rather than actualized speed. *It does not offer data about an algorithm's actual runtime*.
  + Big O is a mathematical mechanism for measuring algorithmic scalability for worst-case behavior scenarios (input level associated with maximal processor burden).
  + Consequently: tests of input data and individual data structures still need to be performed.

<hr />

## 2. <a name="examples">Code Examples</a>

**O(1) - Constant Time:** Algorithms with this complexity consistently execute in the same amount of time, regardless of input size. Retrieving an element (by index) from an array by index occurs in *constant time*. It utilizes just one operation, no matter the array's size:

```
public class ConstantTime {
    public int getFirstElement(int[] array) {
        return array[0]; // Retrieve first element of the specified array
    }

    public static void main(String[] args) {
        ConstantTime constTime = new ConstantTime();
        int[] array = {1, 2, 3, 4, 5};
        System.out.println("First Element: " + constTime.getFirstElement(array));
    }
}
```

**O(log n) - Logarithmic Time:** Algorithms with this complexity reduce problem size by a constant factor for each step/iteration of processing. Binary searches of sorted arrays are popular examples (they reduce problem size, or divide search interval, by half for each iteration):

```
public class LogarithmicTime {
    public int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (array[middle] == target) {
                return midle;
            } else if (array[middle] < target) {
                left = middle + 1;
            } else {
                right = middle - 1;
            }
        }
        return -1; // The target is not found.
    }

    public static void main(String[] args) {
        LogarithmicTime logTime = new LogarithmicTime();
        int[] array = {1, 2, 3, 4, 5, 6, 7};
        int target = 5;
        System.out.println("The index of " + target + "is: " + logTime.binarySearch(array, target));
    }
}
```

**O(n) - Linear Time:** Algorithms with this complexity grow lineraly along with the input size. For example, finding the maximum value in an integer array (this iterates/runs through the array one time, executing a constant time operation for each individual element):

```
public class LinearTime {
    public int findMax(int[] array) {
        int maxVal = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] > maxVal) {
                maxVal = array[i];
            }
        }
        return maxVal;
    }

    public static void main(String[] args) {
        LinearTime linTime = new LinearTime();
        int[] array = {2, 7, 3, 4, 1, 6};
        System.out.println("The maximum element is: " + linTime.findMax(array));
    }
}
```

**O(n log n) - Linearithmic Time:** Algorithms with this complexity are commonly used in sorting algorithms. For example, consider Merge Sort, which divides an array into two halves recursively (*O(log n)*) and then merges those halves (*O(n)*), which ultimately results in linearithmic time (*O(n log n)*):

```
public class LinearithmicTime {
    public void mergeSort(int[] array, int left, int right) {
        if (left < right) {
            int middle = left + (right - left) / 2;
            mergeSort(array, left, middle);
            mergeSort(array, middle + 1, right);
            merge(array, left, middle, right);
        }
    }

    private void merge(int[] array, int left, int middle, int right) {
        int n1 = middle - left + 1;
        int n2 = right - middle;
        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        for (int i = 0; i < n1; i++) {
            leftArray[i] = array[left + i];
        }
        for (int j = 0; j < n2; j++) {
            rightArray[j] = array[middle + 1 + j];
        }

        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (leftArray[i] <= rightArray[j]) {
                array[k++] = leftArray[i++];
            } else {
                array[k++] = rightArray[j++];
            }
        }
        while (i < n1) {
            array[k++] = leftArray[i++];
        }
        while (j < n2) {
            array[k++] = rightArray[j++];
        }
    }

    public static void main(String[] args) {
        LinearithmicTime linTime = new LinearithmicTime();
        int[] array = {40, 20, 17, 8, 23, 4};
        linTime.mergeSort(array, 0, array.length - 1);
        System.out.print("The sorted array: ");
        for (int val : array) {
            System.out.print(val + " ");
        }
    }
}
```

**O(n²) - Quadratic Time:** Algorithms with this complexity utilize nested loops. Consider the following Bubble Sort example, which takes adjacent elements and compares and swaps them in nested loops:

```
public class QuadraticTime {
    public void bubbleSort(int[] array) {
        int n = array.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    // Swap the elements.
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        QuadraticTime quadTime = new QuadraticTime();
        int[] array = {52, 59, 17, 33, 12, 24};
        quadTime.bubbleSort(array);
        System.out.print("The sorted array is: ");
        for (int val : array) {
            System.out.print(val + " ");
        }
    }
}
```

**O(2ⁿ) - Exponential Time:** Algorithms with this complexity have very fast, exponential growth rates. They are commonly used in recursive algorithms, such as the popular solution of the naive Fibonacci sequence (due to it making two recursive calls for each 'n'... which develops a binary tree of call branches, composed of approximately 2ⁿ nodes):

```
public class ExponentialTime {
    public int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        ExponentialTime expTime = new ExponentialTime();
        int n = 10;
        System.out.println("The Fibonacci number at position #" + n + ": is " + et.fibonacci(n));
    }
}
```

<hr />

## 3. <a name="summary">Summary Table of Code Examples</a>

| *Complexity* | *Algorithmic Example* | *Performance Explanation/Summary* |
| :---: | :---: | :----: |
| **O(1)** | Retrieving an element from an array. | Constant time, regardless of input size ('n'). |
| **O(log n)** | Binary search. | Problem size reduces by a constant value (half, in binary search example) for each step. |
| **O(n)** | Linear search, such as finding the maximum value in an integer array. | Grows linearly with input size ('n'). |
| **O(n log n)** | Merge sort. | This complexity is the end result of combining linear and logarithmic complexities. |
| **O(n²)** | Bubble sort. | The performance result of nested loops. |
| **O(2ⁿ)** | Naive Fibonacci. | Exponential scaling, as a result of recursive branching. |

<hr />

## 4. <a name="supplemental">Supplemental Resources</a>

* *[Java Data Structure Leetcode Interview Questions](https://github.com/chaseofthejungle/java-data-structure-leetcode-interview-questions)*
* *[Java Quick Reference Guide](https://github.com/chaseofthejungle/java-quick-reference-guide)*
* *[Intro to the Java Collections Framework](https://github.com/chaseofthejungle/intro-to-java-collections-framework)*
