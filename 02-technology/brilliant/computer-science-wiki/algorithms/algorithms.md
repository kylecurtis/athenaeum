# Algorithms

An algorithm is a procedure that takes in input, follows a certain set of steps, and then produces an output. Oftentimes, the algorithm defines a desired relationship between the input and output. For example, if the problem that we are trying to solve is sorting a hand of cards, the problem might be defined as follows:

> **DEFINITION**
> 
> **Problem:** Sort the input.  
> **Input:** A set of 5 cards.  
> **Output:** The set of 5 input cards, sorted.  
> **Procedure:** Up to the designer of the algorithm!

This last part is very important, it's the meat and substance of the algorithm. And, as an algorithm designer, you can do whatever you want to produce the desired output! Think about some ways you could sort 5 cards in your hand, and then click below to see some more ideas.

1. We could simply toss them up in the air and pick them up again. Maybe they'll be sorted. If not, we can try it again and again until it works (spoiler: this is a bad algorithm).
    
2. We can sort them one at a time, left to right. Let's say our hand looks like {2, 4, 1, 9, 8}. Well, 2 and 4 are already sorted. But then we have a 1. That should go before 4, and it should go before 2. Now we have {1, 2, 4, 9, 8}. 9 is in the right spot because its higher than the card to its left, 4. But 8 is wrong because it's smaller than 9, so we'll just put it before 9. Now, we have {1, 2, 4, 8, 9}, and we're done. This is called [insertion sort](https://brilliant.org/wiki/insertion-sort/).
    
3. We can sort them two at a time, left to right. So, our hand is again {2, 4, 1, 9, 8}. 2 and 4 are good. 4 and 1 need to be swapped, so now we have {2, 1, 4, 9, 8}. 4 and 9 are good. 9 and 8 should be swapped, so now we have {2, 1, 4, 8, 9}. We have to start at the beginning again, but that's no problem. We look at the first pair and see that 2 and 1 need to switch, so now we have {1, 2, 4, 8, 9}, and we're done. This is called [bubble sort](https://brilliant.org/wiki/bubble-sort/).
    
4. There are a million ways to sort this hand of cards! Some are great, most are terrible. It's up to you as the algorithm designer to make a great one.
    

The study of algorithms involves finding the best ways to achieve the desired output given an input and a goal. Learning about algorithms is essential to being a successful computer programmer, and understanding them can help give you an idea of how computers work. So, if you'd like to learn to code, it's absolutely essential to learn about algorithms.

## Contents

- Algorithms and Computers
- Properties of Algorithms
- Types of Algorithms
- Designing an Algorithm
- Analyzing and Evaluating an Algorithm
- Hard Algorithms

## Algorithms and Computers

Even though algorithms existed before the modern computer, they lie at the heart of computing and technology. Everything you've ever done on any piece of technology relies on algorithms because they tell technology what to do. Algorithms are responsible for your ability to surf the web at tolerable speeds. Imagine that you're visiting a website, and that website has a lot of unsorted content to show you. If it randomly picked a content order every time you visited it, and threw that order away and tried again if it wasn't correct, you'd be waiting for minutes, hours, or even days before your web page loaded!

Studying computer science and computer programming always involves algorithms because the study of algorithms teaches you to think like a machine so that you can program them in the best way possible. If you'd like to learn how to write applications, make websites, or do data analysis, you need to know about algorithms so that your code will run fast and run correctly.

On the theoretical side, many of the simpler algorithms have long since been discovered and heavily studied, but there are many areas left to research. For example, in theoretical computer science, a lingering question is whether [P = NP](https://brilliant.org/wiki/p-vs-np/), or in other words, "Are problems that can be quickly verified by a computer able to be quickly solved by a computer?" Currently, we don't think so. But if it turned out to be true, then computing and technology would experience an enormous speed increase that we would all benefit from. However, this would also mean that modern [cryptography](https://brilliant.org/wiki/cryptography/) is not safe and any hacker could easily crack codes to any system in the world!

As computing grew, applications of computing grew along with it. In order to perform the algorithms that would enable those applications, computer scientists needed a way to represent and store that data. If we wanted to input a set of cards into a computer program, how would we store that data? How would we feed it into the algorithm? Early on, it was good enough to simply represent data as computer bits (zeroes and ones). However, that method could never last, it was too difficult and time-consuming.

[Data structures](https://brilliant.org/wiki/linear-data-structures/) were the answer. Their invention and research is paralleled by, and is often taught alongside, algorithms. The card sorting algorithm, for example, could take in an [array](https://brilliant.org/wiki/arrays/) of numbers to represent cards. More data structures were invented over time, and they allowed algorithm design to progress with them. With these in place, it became much easier to reason about, develop, and research algorithms.

## Properties of Algorithms

Algorithms have 3 main properties that are important to remember during their design and analysis.

> **DEFINITION**
> 
> **Algorithm Properties:**
> 
> 1. **Time complexity.** This is the time an algorithm takes to complete, and it is often given using [big O notation](https://brilliant.org/wiki/big-o-notation/) with its input as the independent variable. For example, if we want to search a card in the sorted n cards, we can do in logarithmic time, and the time complexity would be O(log(n)).
>     
> 2. **Space complexity.** This is the space (in computer memory) the algorithm uses during its execution. Again, if we're sorting n cards, and we need to make an extra array of size n for each card to do so, the space complexity would be O(log(n²)).
>     
> 3. **Correctness.** An algorithm is correct if and only if, for every input, it halts and outputs the correct output. Contrary to what you might think, algorithms that are not correct are sometimes useful. For example, [partially correct algorithms](https://brilliant.org/wiki/partial-correctness/) only guarantee that if the algorithm halts, the answer will be correct.
>     

An algorithm can be expressed in a variety of ways, many of which you'll find in different wikis here on Brilliant.

> **DEFINITION**

A few examples of how an algorithm can be described are as follows:

1. **A high-level description.** This might be in the form of text or prose that describes the algorithm: it's input, output, and goal. Generally, this does not involve implementation details of the algorithm.
    
2. **Formal definition.** A formal definition will often give the input and output of the algorithm in formal mathematical terms. The procedure by which the output is achieved is also formally notated. This is a more mathematical way of representing an algorithm.
    
3. **Pseudo-code.** This is a way of loosely formalizing an algorithm, and it is often used when learning algorithms. There are general implementation details; however, language-specific details are left out so as not to complicate things.
    
4. **Implementation.** An implementation in a given language will be a piece of code that is understandable and runnable by a computer. It will fulfill the goals and procedure of the algorithm; however, it is harder to include high-level detail in an implementation because a computer will reject plain text.
    

## Types of Algorithms

There are many types of algorithms, and the language that describes them varies from textbook to textbook and from person to person. Some algorithm labels describe their function, and others describe the process by which they perform their function.

For example, there is a type of algorithm called [string matching algorithms](https://brilliant.org/wiki/string-matching-algorithms/); these algorithms find occurrences of an input string in larger strings or pieces of text. An example of a string matching algorithm is the [Rabin-Karp algorithm](https://brilliant.org/wiki/rabin-karp-algorithm/), but there are many more. On the other hand, an example of a label that describes an algorithm's method for solving the problem is the [divide and conquer algorithm](https://brilliant.org/wiki/divide-and-conquer/). An example of this is [binary search](https://brilliant.org/wiki/binary-search/), which searches for a target in sorted input by cutting up the input into smaller pieces until the target is found.

A specific algorithm can span both classes. For example, a sorting algorithm that performs its sorting [recursively](https://brilliant.org/wiki/recursion/) could be described as either a sorting function or a recursive function.

**Labels that describe function:**

|Algorithm Label|Description|
|---|---|
|Sorting algorithms|Sort a list of comparable inputs.|
|[Graph algorithms](https://brilliant.org/wiki/graph-algorithms/)|Perform elementary graph algorithms such as search.|
|[Shortest path algorithms](https://brilliant.org/wiki/shortest-path-algorithms/)|Find the shortest path(s) between points in a graph.|
|[String matching algorithms](https://brilliant.org/wiki/string-matching-algorithms/)|Search larger pieces of text for input strings.|
|[Max-flow algorithms](https://brilliant.org/wiki/max-flow-min-cut-algorithm/)|Calculate the maximum flow in a flow network.|
|[Computational geometry algorithms](https://brilliant.org/wiki/computational-geometry-algorithms/)|A branch of algorithms that can be stated in terms of geometry|
|[Number-theoretic algorithms](https://brilliant.org/wiki/number-theoretic-algorithms/)|Algorithms that deal with number theory such as [GCD](https://brilliant.org/wiki/greatest-common-divisor/)|
|[Fast fourier transform algorithms](https://brilliant.org/wiki/fast-fourier-transform-algorithms/)|Efficient algorithms that perform [fourier transform](https://brilliant.org/wiki/discrete-fourier-transform/)|
|[Matrix algorithms](https://brilliant.org/wiki/matrix-algorithms/)|Algorithms that perform operations on matrices|

**Labels that describe process:**

|Algorithm Label|Description|
|---|---|
|Divide and conquer algorithms|Divide problem into smaller subproblems that can be recombined for an answer.|
|[Greedy algorithms](https://brilliant.org/wiki/greedy-algorithm/)|Simple, naive approaches to problems that typically return sub-optimal answers|
|[Dynamic programming](https://brilliant.org/wiki/problem-solving-dynamic-programming/) algorithms|Create smaller subproblems whose answers help solve larger and larger subproblems.|
|[Recursive](https://brilliant.org/wiki/recursive/) algorithms|Algorithms that continuously call upon themselves to solve smaller and smaller problems until a basis is formed for the final solution|
|[Brute force algorithms](https://brilliant.org/wiki/brute-force-algorithms/)|An approach to solving problems that attemps to solve the problem with more computing power, rather than elegance|
|[Backtracking algorithms](https://brilliant.org/wiki/backtracking-algorithms/)|Algorithms that build collections of partial candidates for solutions, forgetting them only when they become impossible|
|[Probabilistic and randomized algorithms](https://brilliant.org/wiki/randomized-algorithms-overview/)|Algorithms that use any form of randomization (also called non-deterministic algorithms)|
|[Approximation algorithms](https://brilliant.org/wiki/approximation-algorithms/?wiki_title=Approximation%20algorithms)|Methods that attempt to cut down on computation time by making approximations, getting within some factor of the optimal answer|
|[Multi-threaded algorithms](https://brilliant.org/wiki/multi-threaded-algorithms/?wiki_title=Multi-threaded%20algorithms)|Algorithms that run on multiple [threads](https://brilliant.org/wiki/threads/) to parallelize work|
|[Linear programming algorithms](https://brilliant.org/wiki/linear-programming-algorithms/)|Solutions that achieve optimal answers by using linear relationships of the inputs|

## Designing an Algorithm

When designing an algorithm, it is important to remember that computers are not infinitely fast and that computer memory is not infinitely large. That's why we make algorithms, after all. So, maybe you're designing an algorithm for a computer that is super fast but doesn't have much memory. Maybe you'll make some concessions on the computational requirements so that you can save memory.

But even if you never had to worry about speed or space, you still need to design a good algorithm. Why? You need to design a good algorithm because you need to know that the algorithm will do what you want it to do and that it will stop once it's done. You need to know that it will be correct.

### Efficacy

The efficacy of the algorithm you're designing comes down to time complexity and space complexity. In an ideal world, the algorithm is efficient in both ways, but there is sometimes a tradeoff between them. It is up to the designer to weigh their needs appropriately in order to strike a balance.

It is also up to the designer to make a good algorithm. Doing so requires an understanding of algorithms as well as an understanding of existing algorithms to guide your design process. Otherwise, they might find themselves with a bad algorithm.

Two algorithms that do the same exact thing in different ways could have enormous differences in efficacy. In sorting, for example, [bubble sort](https://brilliant.org/wiki/bubble-sort/) requires O(n) space during its execution. [Quick sort](https://brilliant.org/wiki/quick-sort/), on the other hand, requires O(n lg(n)) space. What does that mean for the programmer using those algorithms? Let's assume for simplicity that the input is just 1KB of data (or 8000 bits). Quicksort will require lg(8000) times more space, or almost 13 times more space than bubble sort. Scale that up to inputs of 1GB or even 1TB, and this difference becomes very noticeable and very inefficient.

However, it's worth noting that quicksort runs faster than bubble sort by the same factor. Again, it's a tradeoff, and it's up to the designer to understand the tradeoffs and to optimize their design for their needs.

## Analyzing and Evaluating an Algorithm

The analysis and evaluation of an algorithm is a two-step process. In the analysis portion, the algorithm is studied to learn about its properties: time/space complexity and correctness. Any method of describing the algorithm, as enumerated above, can be studied. However, that description must contain enough information about the inner workings of the algorithm to provide a clear picture of its procedure.

In general, there are a few ways to describe time complexity. There's the best-case, the average-case, and the worst-case for the algorithm. As a programmer, it's important to know each case so that you fully understand how your algorithm will operate. Which case you focus on is up to you, but the worst-case performance is often used as a benchmark for algorithms.

The evaluation portion is more qualitative and requires the observer to make decisions about the efficacy of the algorithm on its own, and as it relates to other similar algorithms. You might see the algorithm and notice that it is making some critical errors that increase its runtime. You might also discover that its runtime is drastically different than other algorithms that accomplish the same thing. In either case, the evaluation result is poor.

Let's take a look at the pseudo-code for an algorithm and try to analyze its time complexity. The following pseudo-code is that of [insertion sort](https://brilliant.org/wiki/insertion/), a basic sorting algorithm. It takes as its input an array, A, of the number and returns that same array, sorted. Note that this pseudo-code assumes 1-indexing (the first index in the array is 1, not 0).

> **EXAMPLE**
> 
> ```
> Insertion_Sort(A)
> 1    for j = 2 to j = A.length:
> 2        current = A[j]
> 3        i = j - 1
> 4        while i > 0 and A[i] > current:
> 5            A[i+1] = A[i]
> 6            i = i - 1
> 7        A[i + 1] = current
> ```

**Show Answer**

First, let's look at what this code is doing. We are given an input array of numbers, let's say [4, 2, 3, 7, 8]. The algorithm iterates through that array, starting with the second element, in this case, 2. It calls this number current. It grabs the index right before current, which is 1 and whose value is 4, and sets it equal to i. Now it wants to move 4 to the correct location. The while loop says "while the index i is more than 0, and while the number 2 is greater than its neighbor to the left, move 2 to the left and decrease i by 1". So, 2 is moved until it's in the correct spot with respect to the numbers seen so far by the algorithm.

This pseudo-code can be analyzed by looking through this code line by line. In line 2, it has a [for loop](https://brilliant.org/wiki/for-loops/) that iterates from the value 2 to the value A.length which is our input size, n. So, already we know for a fact that this algorithm is at least dependent linearly on our input size. In other words, the runtime of this algorithm is at least O(n) or Ω(n).

Everything inside the for loop must be executed n times, so we can ignore constant time operations such as lines 3, 4, and 8. Instead, line 5 is where the focus must shift because it is another iterable loop.

The [while loop](https://brilliant.org/wiki/while-loops/) on line 5 is similar to the for loop on line 2, but it has a variable number of times it can be repeated. That number can vary from 1 to n depending on how sorted our array is initially. If the input array is [2, 3, 4, 7, 8], for example, the while loop will only run 1 time because each element is not greater than the element to its left. However, if the input is [8, 7, 4, 3, 2], the while loop will need to run O(n) times. To see why, let's see what the array looks like after each iteration of the while loop:

```
0 (input). [8, 7, 4, 3, 2]
1:         [7, 8, 4, 3, 2]
2:         [4, 7, 8, 3, 2]
3:         [3, 4, 7, 8, 2]
4:         [2, 3, 4, 7, 8]
```

See how between the 3rd and 4th iteration the 2 had to move all the way across the array? That's O(n) times.

So, the for loop on line 2 iterates O(n) times. And the while loop on line 5 iterates anywhere from O(1) to O(n) times. So, the best-case runtime is O(n) when the input list is already sorted, and the worst-case is O(n²) when it is sorted in reverse order. The average-case is a little trickier to understand. Basically, we'd expect any element in the input array to be less than half the elements to its left. Half of the elements is still n/2, which is still O(n), so the average-case is also O(n²).

> **TRY IT YOURSELF**
> 
> The following pseudo-code represents an algorithm that takes as input an array of elements that can contain either positive integers or strings. In other words, the input could look like this [42, 'a', 1, 'hello', 3].
> 
> The algorithm outputs an array with the following properties: elements in the output alternate between being a string and being an integer, and each element is less than or equal to the previous element of the same type (except for the elements at position 1 and 2, which are the largest of their respective types). In computer science, it is possible to sort strings ('b' > 'a', for example). This output will contain more elements than the input if the input does not have the same number of integers and strings.
> 
> What is the runtime of this algorithm?
> 
> For this example, assume that the sorting algorithm Reverse_Cheating_Sort(A) is a constant O(1) operation.
> 
> ```
> Crazy_Sort(A):
> 1     strings = []
> 2     integers = []
> 3     num_strings = 0
> 4     num_integers = 0
> 5     for i = 1 to i = A.length:
> 6         if type(A[i]) == 'string':
> 7             num_strings = num_strings + 1
> 8             strings.push(A[i])
> 9         else:
> 10            num_integers = num_integers + 1
> 11            integers.push(A[i])
> 12    if num_strings > num_integers:
> 13        for i = 1 to i = num_strings - num_integers:
> 14            integers.push(1)
> 15    else if num_integers > num_strings:
> 16        for i = 1 to i = num_integers - num_strings:
> 17            strings.push('a')
> 18    result = []
> 19    strings = Reverse_Cheating_Sort(strings)
> 20    integers = Reverse_Cheating_Sort(integers)
> 21    for i = 1 to i = strings.length:
> 22        result.push(strings[0])
> 23        result.push(integers[0])
> 24    return result
> ```
> 
> The correct answer is:
> 
> - O(1)
> - O(n)
> - O(2n)
> - O(n²)

## Hard Algorithms

Typical algorithms are generally efficient. They run in polynomial time. In other words, their runtime can be defined as O(nˣ) for some input n and some integer x. However, there is a class of algorithms that do not currently have a polynomial-time solution. Some famous examples of this are the [traveling salesperson problem](https://brilliant.org/wiki/traveling-salesperson-problem/) or the [set cover problem](https://brilliant.org/wiki/set-cover-problem/?wiki_title=set%20cover%20problem).

These problems are called NP-complete problems and are very interesting to study. Although no polynomial-time algorithm has ever been discovered for them, no one has proven that there can't be one out there, waiting to be discovered. Furthermore, if a solution was found for just one of them, a solution could be inferred for all of them!

There are currently various algorithms that make good approximations for solutions to these problems. They might use [heuristics](https://brilliant.org/wiki/heuristics/) to cut down on runtime. However, the answer is not always exact, and the algorithm is therefore not correct.

The field of computer science contains many exciting areas to explore. In theory and algorithms, the question of NP-completeness and its relationship to other algorithms is one that has puzzled computer scientists for decades and that has many important implications for technology and for the world.

---

_Cite as: Algorithms. Brilliant.org. Retrieved 02:43, September 24, 2025, from https://brilliant.org/wiki/algorithm/_