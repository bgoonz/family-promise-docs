# Intervi

Checklist: Preparing for Your Interview Labs Interview Prep Checklist Here's how to prepare in the days before your interview:

☐ Use your pull request videos as an opportunity to practice walking through a project. Incorporate feedback from your Release Manager and keep iterating (trying again)!

☐ Practice describing your project to someone who has never seen it.

What is it? Why was it built? How does it work? ☐ Practice describing relevant technologies to someone unfamiliar with the technology.

What is Redux? Why do you use it? What do you like about it? Why is it the best choice for this project? ☐ For extra practice, try using Pramp for mock interviews with peers!

Pramp instructions:

Step 1: Set up account in Pramp (Links to an external site.)

Step 2: Select the type of interview you want to prep for

Step 3: Schedule mock interviews with an anonymous peer, or invite a Lambda buddy to interview with using the “invite session” feature. We highly recommend scheduling any Pramp mock interviews on separate days so you have time to reflect and improve in between.

Once you've completed this checklist, mark this page as "done" below.

Bonus: Zero-Hour Checklist Follow these steps leading up to the interview itself to set yourself up for success! 🚀

As early as possible ☐ Make sure you have your 1️⃣ Tell me about yourself ready to go.

30 minutes before interview ☐ Set up a quiet place to do the interview

☐ Make sure that you are in a spot with good lighting, a clean background (and one where no one can walk through the background!)

☐ Wear the same outfit you would wear if the interview was in person

☐ Have a notebook/note-taking method of choice ready

☐ Water🚰 beside you! Staying hydrated during stressful situations is key!

15 minutes before interview ☐ Be ready and in position for the interview

5 minutes before interview ☐ Remind yourself how awesome you are. Really. Say it out loud if possible.

☐ Practice your favorite relaxation/grounding practice. This could be doodling, deep breathing, or listening to a favorite pump-up song. You want to make sure that you are well-positioned to put a centered and positive foot forward from the first "hello!"



Home page Help Lambda School Labs Interview Please follow the instructions to book online.

Thank you. Powered by OnceHub Your booking is confirmed An email confirmation was sent to bryan.guner@gmail.com. An event was added to your bryan.guner@gmail.com calendar. Your booking details Meeting type: Lambda School Labs Interview Team member: Godknows S Time: Thu, Oct 21, 2021, 5:00 PM - 6:00 PM United States; Eastern time (GMT-4:00) \[DST] Conferencing information: Please join your Zoom interview using the following link at the scheduled time: https://us04web.zoom.us/j/3638914020?pwd=MmNiaXdsSFlJZlBrYjZHM1kyQS9CZz09 Booking ID: BKNG-TSLJA9WXCY0Nall pairs of two integers in an unsorted array that add up to a target.





## Find all the pairs of two integers in an unsorted array that sum up to a given S.

## For example, if the array is \[3, 5, 2, -4, 8, 11] and the sum is 7, your program should return \[\[11, -4], \[2, 5]]

## because 11 + -4 = 7 and 2 + 5 = 7.

## array = \[3, 5, 2, -4, 8, 11]







**Understanding the problem**

**Problem Description: **Given an array of n integers and given a number K, determines whether there is a pair of elements in the array that sums to exactly K.

**For example :**

Input : A\[] = \[-5, 1, -40, 20, 6, 8, 7 ], K=15

Output: true ( 7, 8 and -5, 20 are the pairs with sum 15)

Input : A\[] = \[-5, 4, -2, 16, 8, 9], K=15

Output: false (There is no pair of elements whose sum is equal to 15)

**Possible follow-up questions to ask the interviewer :**

* Do we know something about the range of the numbers in the array? **Ans:** No, they can be arbitrary integers.
* Are the array elements necessarily positive? **Ans:** No, they can be positive, negative, or zero.
* Do we know anything about the value of K relative to the numbers in the array? **Ans:** No, it can be arbitrary.
* Can we consider pairs of an element and itself? **Ans:** No, the pair should consist of two different array elements.
* Can the array contain duplicates? **Ans:** Sure, that's a possibility.

**Designing efficient solutions**

We are discussing four ways to solve this problem :

1. Brute force Approach: Using two loops
2. Sorting and binary search
3. Sorting and two Pointer approach
4. Using a Hash Table

**1. Brute Force Approach: Using two loops**

Use two loops and check A\[i] + A\[j] == K for each pair (i, j) in A\[]. If there exists a pair with sum equals to K then return true. By end of both loops, If you didn’t find such a pair then return false.

> **Pseudo Code**

```java
int find_sumPair (A[], n, K)
{
  for( i = 0 to n-1 )
  {
     for(j = i+1 to n-1)
     { 
         if(A[i]+A[j] == K)
         return 1
     }
  }
return -1
}
```

> **Complexity Analysis**

The total no. of comparison in worst case = Total no. of possible pairs = nC2 = n(n-1)/2 = O(n²)

Time Complexity = O(n²) and Space Complexity = O(1). Can we improve the time complexity? Let's try to think about it.

**2. Sorting and Binary Search**

The idea of binary search works perfectly in the case of the sorted array. We can sort the A\[] and for each value A\[i], search whether there is another value K-A\[i] present in the array or not. Binary search performs searching in O(logn) which could help us to improve the time complexity.

> **Solution Steps**

* Sort the array A\[] in increasing order
* For each element A\[i], use binary search to look for K-A\[i].
* If there exists a value K-A\[i] in the array A, then return true.
* If you didn’t find such a pair in the whole array , then return false.

> **Pseudo Code**

```java
int find_sumPair (A[], n, K)
 {
   Sort ( A, n)
   for( i = 0 to n-1 )
   { 
      x = binarySearch ( A, 0, n-1, K-A[i] )
      if ( x ) 
      return 1
   }
 return -1
 }
```

> **Complexity Analysis**

Suppose we are using heap sort/merge sort and iterative binary search for the implementation.

Time Complexity = Time complexity of sorting + n. Time complexity of Binary Search = O(nlogn) + n. O(logn) = O(nlogn)

Space Complexity = Space Complexity of sorting + Space complexity of the binary search (Iterative Implementation)

If merge sort ,Space Complexity = O(n) + O(1) = O(n)

If Heap Sort, Space Complexity = O(1) + O(1) = O(1)

> **Critical Ideas to think!**

* What would be the time and space complexity if we use quicksort? Compare different sorting algorithms
* What would be the space complexity of the recursive binary search?
* Why are we searching K - A\[i] for each element in array A\[]?
* Prepare a list of problems where you can apply the idea of sorting and binary search.

**3. Sorting and two Pointer approach**

Sort the array A\[] then walk two pointers inward from the ends of the array, at each point looking at their sum. If it is exactly k, then we are done. If it exceeds k, then any sum using the larger element is too large, so we walk that pointer inwards. If it is less than k, then any sum using the lower element is too small, so we walk that pointer inwards.

> **Solution Steps**

1. Sort the array A\[] in increasing order
2. Initialize two index variables in the sorted array A\[].

* left pointer: i = 0
* right pointer : j = n-1

3\) Run a loop while i< j.

* If (A\[i] + A\[j] == K) then return true
* if( A\[i] + A\[j] < K) then increment i by 1
* if( A\[i] + A\[j] > K) then decrement j by 1

4\) If didn’t find such a pair in the whole array - return false.

> _**Solution Visualization**_

![](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/check-for-pair-in-an-array-with-a-given-sum_two_pointer.jpg)

> **Pseudo Code**

```java
int find_sumPair( A[], n, K)
 { 
    Sort(A, n)
    i = 0
    j = n -1 
    while (i < j)
    {
       if(A[i] + A[j] == K)
         return 1
       else if(A[i] + A[j] < K)
         i = i+1
       else
         j = j-1
    } 
 return -1
 }
```

> **Complexity Analysis**

Suppose we are using Heap Sort or merge sort.

Time Complexity = Time complexity of sorting + Time complexity of two pointer approach (while loop) = O (n log n) + O(n) = O (n log n)

If merge sort, Space Complexity = O(n)

If Heap Sort, Space Complexity = O(1)

> **Critical Ideas to think!**

* is this algorithm works fine if elements are repeated?
* The time complexity of while loop is O(n) in the worst-case - why?
* Why the idea of the two pointer approach works perfectly for a sorted array?
* Prepare a list of problems where you can apply the idea of two pointer approach for the solution.

![Thumbnail Image](https://afteracademy.com/assets/android-course-subscription-banner.png)

NEW

**Android App Development Online Course by MindOrks**

Start your career in Android Development. Learn by doing real projects.

[CHECK NOW](https://mindorks.com/android-app-development-online-course)

**4. Using a Hash Table**

Idea is to use the Hash Table to improve the time complexity because it performs searching and insertion efficiently in O(1) average.

> **Solution Steps**

1. Take a Hash Table H of size O(n)
2. Run a loop and scan over the array A\[] for each A\[i]. Check if K-A\[i] is present in the hash table or not.

* If yes, we have found the pair and return true.
* If no, then insert A\[i] into the Hash table

3\. If you didn’t find such a pair by end of the loop then return false.

> **Pseudo Code**

```java
bool checkPair(int A[], int n, int K) 
{ 
  Take Hash Table H of size O(n)
  for (i = 0 to n-1)
  { 
      int x = K - A[i]
      if (H.search(x) is true) 
          return 1
      H.insert(A[i]) 
  } 
 return -1
} 
```

> **Complexity Analysis**

In worst case scenario, we scan the whole array and didn't find any such pair. Time Complexity = Time complexity of inserting n elements in hash table + Time complexity of searching (K-A\[i]) n times in hash table = n. O(1) + n . O(1) = O(n)

Space Complexity = Extra space of Hash Table = O(n)

> **Critical Ideas to think!**

* is this algorithm works fine if elements are repeated?
* What would be the time and space complexity if we use a binary search tree in place of a hash table? Compare hash table and binary search tree
* This is also a good example of problem-solving via data structure. Prepare a list of problems where we use data structures (hash table, BST, priority queue, stack, queue, etc) for the efficient solution.
* Is there any other way to solve this problem? Think

**Comparison of the different solutions**

![](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/check-for-pair-in-an-array-with-a-given-sum_sol_comparison.png)

**Similar Problems to solve**

1. Given an array of integers, and a number K, print all pairs in the array whose sum is equal to K.
2. Given an array and a value, find if there is a triplet in the array whose sum is equal to the given value.
3. Check for pair with a given sum in Binary Search Tree
4. Given two unsorted arrays(elements in every array are distinct), find the intersection of two arrays
5. Given an unsorted array of integers, find the length of the longest consecutive sequence.
6. Given two integer array A\[] and B\[] of size m and n(n <= m) respectively. We have to check whether B\[] is a subset of A\[] or not.

## Find a pair with the given sum in an array

Given an unsorted integer array, find a pair with the given sum in it.

For example,

**Input:**\
 \
arr = \[8, 7, 2, 5, 3, 1]\
target = 10\
 \
**Output:**\
 \
Pair found (8, 2)\
or\
Pair found (7, 3)\
 \
 \
**Input:**\
 \
arr = \[5, 2, 6, 8, 1, 9]\
target = 12\
 \
**Output:** Pair not found

> [Practice this problem](https://techiedelight.com/practice/?problem=TwoSum)

There are several methods to solve this problem using brute-force, sorting, and hashing. These are discussed below:

### 1. Using Brute-Force <a href="brute-force" id="brute-force"></a>

A naive solution is to consider every pair in the given array and return if the desired sum is found. This approach is demonstrated below in C, Java, and Python:

* C
* Java
* Python

\


|                                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 12345678910111213141516171819202122232425 | # Naive method to find a pair in a list with the given sumdef findPair(A, target):     # consider each element except the last    for i in range(len(A) - 1):         # start from the i'th element until the last element        for j in range(i + 1, len(A)):             # if the desired sum is found, print it            if A\[i] + A\[j] == target:                print("Pair found", (A\[i], A\[j]))                return     # No pair with the given sum exists in the list    print("Pair not found")  if \__name\_\_ == '\__main\_\_':     A = \[8, 7, 2, 5, 3, 1]    target = 10     findPair(A, target)  |

[Download](https://www.techiedelight.com/code/vfgXZzP)  [Run Code](https://techiedelight.com/compiler/?run=vfgXZzP)

**Output:**\
\
Pair found (8, 2)\


The time complexity of the above solution is O(n2) and doesn’t require any extra space, where `n` is the size of the input.

### 2. Using Sorting <a href="sorting" id="sorting"></a>

The idea is to [sort the given array](https://www.techiedelight.com/sort-array-ascending-order-cpp/) in ascending order and maintain search space by maintaining two indices (`low` and `high`) that initially points to two endpoints of the array. Then reduce the search space `arr[low…high]` at each iteration of the loop by comparing the sum of elements present at indices `low` and `high` with the desired sum. Increment `low` if the sum is less than the expected sum; otherwise, decrement `high` if the sum is more than the desired sum. If the pair is found, return it.

Following is the C++, Java, and Python implementation based on the idea:

* C++
* Java
* Python

\


|                                                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 123456789101112131415161718192021222324252627282930313233343536 | # Function to find a pair in an array with a given sum using sortingdef findPair(A, target):     # sort the list in ascending order    A.sort()     # maintain two indices pointing to endpoints of the list    (low, high) = (0, len(A) - 1)     # reduce the search space \`A\[low…high]\` at each iteration of the loop     # loop till the search space is exhausted    while low < high:         if A\[low] + A\[high] == target:        # target found            print("Pair found", (A\[low], A\[high]))            return         # increment \`low\` index if the total is less than the desired sum;        # decrement \`high\` index if the total is more than the desired sum        if A\[low] + A\[high] < target:            low = low + 1        else:            high = high - 1     # No pair with the given sum exists    print("Pair not found")  if \__name\_\_ == '\__main\_\_':     A = \[8, 7, 2, 5, 3, 1]    target = 10     findPair(A, target)  |

[Download](https://www.techiedelight.com/code/BuxbMfP)  [Run Code](https://techiedelight.com/compiler/?run=BuxbMfP)

**Output:**\
\
Pair found (2, 8)\


The time complexity of the above solution is O(n.log(n)) and doesn’t require any extra space.

### 3. Using Hashing <a href="hashing" id="hashing"></a>

We can use a [hash table](https://www.techiedelight.com/hashing-in-data-structure/) to solve this problem in linear time. The idea is to insert each array element `arr[i]` into a map. We also check if difference `(arr[i], target - arr[i])` already exists in the map or not. If the difference is seen before, print the pair and return. The algorithm can be implemented as follows in C++, Java, and Python:

* C++
* Java
* Python

\


|                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 123456789101112131415161718192021222324252627282930 | # Function to find a pair in an array with a given sum using hashingdef findPair(A, target):     # create an empty dictionary    dict = {}     # do for each element    for i, e in enumerate(A):         # check if pair \`(e, target - e)\` exists         # if the difference is seen before, print the pair        if target - e in dict:            print("Pair found", (A\[dict.get(target - e)], A\[i]))            return         # store index of the current element in the dictionary        dict\[e] = i     # No pair with the given sum exists in the list    print("Pair not found")  if \__name\_\_ == '\__main\_\_':     A = \[8, 7, 2, 5, 3, 1]    target = 10     findPair(A, target)  |

[Download](https://www.techiedelight.com/code/D73rFKP)  [Run Code](https://techiedelight.com/compiler/?run=D73rFKP)

**Output:**\
\
Pair found (8, 2)







Given an array of integers, and a number ‘sum’, print all pairs in the array whose sum is equal to ‘sum’.

```
Examples :
Input  :  arr[] = {1, 5, 7, -1, 5}, 
          sum = 6
Output : (1, 5) (7, -1) (1, 5)

Input  :  arr[] = {2, 5, 17, -1}, 
          sum = 7
Output :  (2, 5)
```

[Recommended: Please solve it on “_**PRACTICE**_” first, before moving on to the solution.](https://practice.geeksforgeeks.org/problems/count-pairs-with-given-sum/0)

A **simple solution** is to traverse each element and check if there’s another number in the array which can be added to it to give sum.

Attention reader! Don’t stop learning now. Get hold of all the important DSA concepts with the [**DSA Self Paced Course**](https://practice.geeksforgeeks.org/courses/dsa-self-paced) at a student-friendly price and become industry ready.  To complete your preparation from learning a language to DS Algo and many more,  please refer [**Complete Interview Preparation Course**](https://practice.geeksforgeeks.org/courses/complete-interview-preparation)**.**

In case you wish to attend **live classes **with experts, please refer [**DSA Live Classes for Working Professionals **](https://practice.geeksforgeeks.org/courses/geeks-classes-live)and [**Competitive Programming Live for Students**](https://practice.geeksforgeeks.org/courses/competitive-programming-live).

* C++
* Java
* Python3
* C#
* PHP
* Javascript

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<script>` `// JavaScript implementation of simple method to// find print pairs with given sum.` `// Returns number of pairs in arr[0..n-1]// with sum equal to 'sum'function` `printPairs(arr, n, sum){    let count = 0; // Initialize result` `    // Consider all possible pairs and check    // their sums    for` `(let i = 0; i < n; i++)        for` `(let j = i + 1; j < n; j++)            if` `(arr[i] + arr[j] == sum)                 document.write("("` `+ arr[i] + ", "                    + arr[j] + ")"` `+ "<br>");}` `// Driver function to test the above function` `    let arr = [ 1, 5, 7, -1, 5 ];    let n = arr.length;    let sum = 6;    printPairs(arr, n, sum);`  `// This code is contributed by Surbhi Tyagi` `</script>` |

**Output :** \
\


```
(1, 5)
(1, 5)
(7, -1)
```

 

**Method 2 (Use hashing)**. \
We create an empty hash table. Now we traverse through the array and check for pairs in the hash table. If a matching element is found, we print the pair number of times equal to the number of occurrences of the matching element. \
Note that the worst case of time complexity of this solution is **O(c + n)** where c is the count of pairs with a given sum.

* C++
* Java
* Python3
* C#
* Javascript

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<script>      // JavaScript implementation of simple method to      // find count of pairs with given sum.      // Returns number of pairs in arr[0..n-1]      // with sum equal to 'sum'      function` `printPairs(arr, n, sum) {        // Store counts of all elements in map m        var` `m = {};` `        // Traverse through all elements        for` `(var` `i = 0; i < n; i++) {          // Search if a pair can be formed with          // arr[i].          var` `rem = sum - arr[i];` `          if` `(m.hasOwnProperty(rem)) {            var` `count = m[rem];` `            for` `(var` `j = 0; j < count; j++) {              document.write("("` `+ rem + ", "` `+ arr[i] + ")"` `+ "<br>");            }          }` `          if` `(m.hasOwnProperty(arr[i])) {            m[arr[i]]++;          } else` `{            m[arr[i]] = 1;          }        }      }` `      // Driver code      var` `arr = [1, 5, 7, -1, 5];      var` `n = arr.length;      var` `sum = 6;` `       printPairs(arr, n, sum);       ` `      // This code is contributed by rdtank.    </script>` |

**Output :** 

```
(1, 5)
(7, -1)
(1, 5)
```

 

**Method 3**. \
Another method to Print all pairs with the given sum is given as follows: 

* C++
* Java
* Python3
* C#
* Javascript

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<script>` `        // Javascript code to implement        // the above approach        function` `pairedElements(arr, sum, n) {            var` `low = 0;            var` `high = n - 1;` `            while` `(low < high) {                if` `(arr[low] + arr[high] == sum) {                    document.write("The pair is : ("` `+                        arr[low] + ", "` `+                        arr[high] + ")<br>");                }                if` `(arr[low] + arr[high] > sum) {                    high--;                }                else` `{                    low++;                }            }        }` `        // Driver code        var` `arr = [ 2, 3, 4, -2, 6, 8, 9, 11]        var` `n = arr.length;        arr.sort(function(a,b){return` `a-b;});        pairedElements(arr, 6, n);`  `    </script>` |

**Output :** 

```
The pair is : (-2, 8)
The pair is : (2, 4)
```

 

