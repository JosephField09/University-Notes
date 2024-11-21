[[Data Structures and Algorithms]]

- One aspect of software development is the efficient use of resources, like the processor 
- Algorithm analysis gives us  a basis to compare the efficiency of algorithms
- To analyse an algorithm means to determine the amount of resources (e.g. time and storage) that is necessary to execute it.

- Analysis is based on:
	- The problem size
	- A key operation

- A growth function T(n) shows the relationship between the size of the problem (n) and the time is takes to solve the problem.

- The problem size is typically expressed in terms of the amount of data needed to be processed .


- The key issue to observe is the asymptotic complexity of the growth function
	- Determined by its dominant term
	- Referred to as the order (type) of the algorithm


| Growth Function                | Order <br>(in Big-O notation) | Name                     | Example                                                                                    |
| ------------------------------ | ----------------------------- | ------------------------ | ------------------------------------------------------------------------------------------ |
| T(n) = 37                      | O(1)                          | Constant                 | Determining if a number is even or odd                                                     |
| T(n) = 24 x log(n) + 11        | O(log n)                      | Logarithmic              | Finding an item in a sorted list using binary search                                       |
| T(n) = 200 + 3n                | O(n)                          | Linear                   | Finding an item in an unsorted list                                                        |
| T(n) = 7n x log(n) + 4n + 1000 | O(n log n)                    | Log-Linear or<br>n log n | sorting a list with a quick sort or heap sort                                              |
| T(n) = $2n^2$ + 5 + 49n        | O($n^2$)                      | Quadratic                | Sorting a list wit insertion sort or selective sort                                        |
| T(n) = 3n + $6n^3$ + 41        | O($n^3$)                      | Cubic                    | Finding the best sum of subsequence over a sequence of numbers using brute force algorithm |
|                                | O($2^n$)                      | Exponential              | Solving the tower of hanoi problem; guessing a password of length n bits                   |


- To distinguish between the relative efficiency of two algorithms in the same O class, use the tilde notation.

- We retain the constant multiplier in the dominant term


- Given a piece of source code, we can determine the order of the underlying algorithm.
	- O(1) typically corresponds to:
		- an assignment statement
		- a conditional statement
		- a return statement
	- O(n) typically corresponds to:
		- a simple loop
	- O($n^2$) typically corresponds to:
		- a nested loop


Analysing Loop Execution
- A loop executes a certain number of times (n)
- The complexity of a loop is n times the complexity of the body of the loop


Software Engineering and Data Structures
- As software grows more complex, we need efficient algorithms to meet users' needs
- In some cases, using an efficient algorithm is more important than having a fast cpu


Average Case and Worst Case Analysis
- Sometimes an algorithm may perform well on average but some special input data sets, it performs noticeably badly