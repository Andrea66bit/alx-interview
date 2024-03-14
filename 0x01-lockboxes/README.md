CODE IS A PROGRAMMED SYSTEM
Asymptotic Notation and Analysis (Based on input size) in Complexity Analysis of Algorithms
Asymptotic Analysis is defined as the big idea that handles the above issues in analyzing algorithms. In Asymptotic Analysis, we evaluate the performance of an algorithm in terms of input size (we don’t measure the actual running time). We calculate, how the time (or space) taken by an algorithm increases with the input size. 

Asymptotic notation is a way to describe the running time or space complexity of an algorithm based on the input size. It is commonly used in complexity analysis to describe how an algorithm performs as the size of the input grows. The three most commonly used notations are Big O, Omega, and Theta.

Big O notation (O): This notation provides an upper bound on the growth rate of an algorithm’s running time or space usage. It represents the worst-case scenario, i.e., the maximum amount of time or space an algorithm may need to solve a problem. For example, if an algorithm’s running time is O(n), then it means that the running time of the algorithm increases linearly with the input size n or less.
Omega notation (?): This notation provides a lower bound on the growth rate of an algorithm’s running time or space usage. It represents the best-case scenario, i.e., the minimum amount of time or space an algorithm may need to solve a problem. For example, if an algorithm’s running time is ?(n), then it means that the running time of the algorithm increases linearly with the input size n or more.
Theta notation (?): This notation provides both an upper and lower bound on the growth rate of an algorithm’s running time or space usage. It represents the average-case scenario, i.e., the amount of time or space an algorithm typically needs to solve a problem. For example, if an algorithm’s running time is ?(n), then it means that the running time of the algorithm increases linearly with the input size n.
In general, the choice of asymptotic notation depends on the problem and the specific algorithm used to solve it. It is important to note that asymptotic notation does not provide an exact running time or space usage for an algorithm, but rather a description of how the algorithm scales with respect to input size. It is a useful tool for comparing the efficiency of different algorithms and for predicting how they will perform on large input sizes.

Why performance analysis? 
There are many important things that should be taken care of, like user-friendliness, modularity, security, maintainability, etc. Why worry about performance?  The answer to this is simple, we can have all the above things only if we have performance. So performance is like currency through which we can buy all the above things. Another reason for studying performance is – speed is fun! To summarize, performance == scale. Imagine a text editor that can load 1000 pages, but can spell check 1 page per minute OR an image editor that takes 1 hour to rotate your image 90 degrees left OR … you get it. If a software feature can not cope with the scale of tasks users need to perform – it is as good as dead. 



How to study efficiency of  algorithms?
The way to study the efficiency of an algorithm is to implement it and experiment by running the program on various test inputs while recording the time spent during each execution. A simple mechanism in Java is based on use of the currentTimeMillis() method of the System class  for collecting such running times. That method reports the number of milliseconds that have passed since a benchmark time known
as the epoch (January 1, 1970 UTC).The key is that if we record the time immediately before executing the algorithm and then immediately after it.

long start = System.currentTimeMillis( ); // record the starting time
 /? (run the algorithm) ?/
 long end = System.currentTimeMillis( ); // record the ending time
 long elapsed = end ? start; //Total time elapsed

Measuring elapsed time  provides a reasonable reflection of an algorithm’s efficiency.

Given two algorithms for a task, how do we find out which one is better? 
One naive way of doing this is – to implement both the algorithms and run the two programs on your computer for different inputs and see which one takes less time. There are many problems with this approach for the analysis of algorithms. 

It might be possible that for some inputs, the first algorithm performs better than the second. And for some inputs second performs better. 
It might also be possible that for some inputs, the first algorithm performs better on one machine, and the second works better on another machine for some other inputs.
Asymptotic Analysis is the big idea that handles the above issues in analyzing algorithms. In Asymptotic Analysis, we evaluate the performance of an algorithm in terms of input size (we don’t measure the actual running time). We calculate, how the time (or space) taken by an algorithm increases with the input size. 

For example, let us consider the search problem (searching a given item) in a sorted array. 

The solution to above search problem includes: 

Linear Search (order of growth is linear) 
Binary Search (order of growth is logarithmic). 
To understand how Asymptotic Analysis solves the problems mentioned above in analyzing algorithms, 

let us say: 
we run the Linear Search on a fast computer A and 
Binary Search on a slow computer B and 
pick the constant values for the two computers so that it tells us exactly how long it takes for the given machine to perform the search in seconds. 
Let’s say the constant for A is 0.2 and the constant for B is 1000 which means that A is 5000 times more powerful than B. 
For small values of input array size n, the fast computer may take less time. 
But, after a certain value of input array size, the Binary Search will definitely start taking less time compared to the Linear Search even though the Binary Search is being run on a slow machine. 
Input Size	Running time on A	Running time on B
10	2 sec	~ 1 h 
100	20 sec	~ 1.8 h
10^6 	~ 55.5 h	~ 5.5 h
10^9	~ 6.3 years 	~ 8.3 h
The reason is the order of growth of Binary Search with respect to input size is logarithmic while the order of growth of Linear Search is linear. 
So the machine-dependent constants can always be ignored after a certain value of input size. 
Running times for this example: 


Linear Search running time in seconds on A: 0.2 * n 
Binary Search running time in seconds on B: 1000*log(n) 
Challenges of Experimental Analysis:
Experimental running times of two algorithms are difficult to directly compare unless the experiments are performed in the same hardware and software environments. Experiments can be done only on a limited set of test inputs; hence, they leave out the running times of inputs not included in the experiment (and these inputs may be important).

To overcome the challenges in the Experimental analysis Asymptotic Analysis is used.

Does Asymptotic Analysis always work? 
Asymptotic Analysis is not perfect, but that’s the best way available for analyzing algorithms. For example, say there are two sorting algorithms that take 1000nLogn and 2nLogn time respectively on a machine. Both of these algorithms are asymptotically the same (order of growth is nLogn). So, With Asymptotic Analysis, we can’t judge which one is better as we ignore constants in Asymptotic Analysis. 

Also, in Asymptotic analysis, we always talk about input sizes larger than a constant value. It might be possible that those large inputs are never given to your software and an asymptotically slower algorithm always performs better for your particular situation. So, you may end up choosing an algorithm that is Asymptotically slower but faster for your software.

Advantages or Disadvantages:
Advantages:
Asymptotic analysis provides a high-level understanding of how an algorithm performs with respect to input size.
It is a useful tool for comparing the efficiency of different algorithms and selecting the best one for a specific problem.
It helps in predicting how an algorithm will perform on larger input sizes, which is essential for real-world applications.
Asymptotic analysis is relatively easy to perform and requires only basic mathematical skills.

Disadvantages:

Asymptotic analysis does not provide an accurate running time or space usage of an algorithm.
It assumes that the input size is the only factor that affects an algorithm’s performance, which is not always the case in practice.
Asymptotic analysis can sometimes be misleading, as two algorithms with the same asymptotic complexity may have different actual running times or space usage.
It is not always straightforward to determine the best asymptotic complexity for an algorithm, as there may be trade-offs between time and space complexity.


Recommended Problems
Frequently asked DSA Problems
Solve Problems
Last Updated : 04 May, 2023

1.28k

Previous
Worst, Average and Best Case Analysis of Algorithms
Next
How to Analyse Loops for Complexity Analysis of Algorithms
Share your thoughts in the comments

Add Your Comment
Similar Reads
Types of Asymptotic Notations in Complexity Analysis of Algorithms
Asymptotic Analysis and comparison of sorting algorithms
Postfix to Prefix converter(Reverse Polish Notation to Polish Notation Converter)
Guidelines for asymptotic analysis
Analysis of Algorithms | Big - Θ (Big Theta) Notation
Analysis of Algorithms | Big - Ω (Big- Omega) Notation
Time Complexity and Space Complexity
Time and Space Complexity Analysis of Tree Traversal Algorithms
Sample Practice Problems on Complexity Analysis of Algorithms
How to Analyse Loops for Complexity Analysis of Algorithms
Complete Tutorials
Learn Algorithms with Javascript | DSA using JavaScript Tutorial
DSA Crash Course | Revision Checklist with Interview Guide
Learn Data Structures and Algorithms | DSA Tutorial
Mathematical and Geometric Algorithms - Data Structure and Algorithm Tutorials
Learn Data Structures with Javascript | DSA using JavaScript Tutorial
https://media.geeksforgeeks.org/auth/avatar.png
GeeksforGeeks
Article Tags :
Complexity-analysis 
Algorithms 
Analysis of Algorithms 
DSA
Practice Tags :
Algorithms
Additional Information

