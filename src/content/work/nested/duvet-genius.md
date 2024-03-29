---
title: Task Placement in Multi-processor System
publishDate: 2024-07-02 00:00:00
img: /assets/stock-3.jpg
img_alt: Illustrative sketch of the project
description: |
   This project is an NP-problem consisting of placing tasks in a multi-processor system using a genetic algorithm 
tags:
  - C Programming
  - Optimisation
  - Genetic Algorithm
---

 This project is an NP problem consisting of placing tasks in a multi-processor system using a genetic algorithm.

 Here is a simulation for 300 individuals in our population and 200 generations (we stop the generation of generations by press 'enter') :

**in progress*

##### 1. Introduction

<div class="justify-text">
We have a set of processes (or tasks) T1,...,Tn of a parallel program and a set of processors P1,...,Pp
</div>

<div class="justify-text">
The processors are not identical and we know for each task Ti its execution cost qij on Pj
</div>

<div class="justify-text">
If Ti and Tj are not placed on the same processor, then there is a communication cost to the exchange of data between these two tasks
</div>

<div class="justify-text">
The communication cost between two tasks placed on a single processor is negligeable
</div>

**The goal of this project is to minimize the total cost of execution, ie the sum of execution and communication costs**


The input format used will be as follows :
- n : number of tasks
- p : number of processors
- Q : execution costs (matrix n x p)
- C : communication costs (matrix n x n symmetrical therefore storage of the upper triangular part)

Display in the terminal which task is associated with which processor

##### 2. NP problem

<div class="justify-text">
This problem is difficult in the sense of complexity. There is most likely no effective algorithm to find optimal solutions
Thus, since it is difficult to determine optimal solutions in a reasonable time, we will use heuristic (fast) approaches to determine good solutions
</div>

##### 3. Genetic algorithm

<p align="justify">
In traditional genetic algorithm, the representation used is a fixed-length bit string.Each position in the string is assumed to represent a particular feature of an individual, and the value stored in that position represents how that feature is expressed in the solution. Usually, the string is “evaluated as a collection of structural features of a solution that have little or no interactions”. The analogy may be drawn directly to genes in biological organisms. Each gene represents an entity that is structurally independent of other genes. The main reproduction operator used is bit-string crossover, in which two strings are used as parents and new individuals are formed by swapping a sub-sequence between the two strings (see Fig. 1.1). Another popular operator is bit-flipping mutation, in which a single bit in the string is flipped to form a new offspring string.
</p>

<p align="justify">
Some problems are too complex to propose an algorithm, or when there is no exact method to solve them, a delicate and/or confusing modeling where the solution to the problem is unknown. Or an algorithm tolerant to data variations, likely to adapt to a new situation, so that it evolves.
For example, how to make the movement of a robot? How to make react this robot following a jostling, a loss of balance? How to adapt the behavior of the robot in the face of danger?
Genetic algorithms offer a solution to these questions.
</p>

<p align="justify">
These algorithms are also an excellent support for the field of Machine Learning, which is a field of study of artificial intelligence. These can be used to optimize a neural network, including training the network through the use of new information in synaptic connections, thus improving network topology to obtain an optimal learning rule: This is called neuroevolution.
</p>

<p align="justify">
Genetic algorithms can also be used to optimize systems based on fuzzy logic, by performing the generation and/or optimization of rules or operators in those systems. 
</p>

The Darwinian theory of evolution is based on two postulates :

- In each environment, only the best adapted species persist over time, the others being condemned to
disparate

- Within each species, population turnover is mainly due to the best individuals of the species

To **define a genetic algorithm:**

1. A function to optimize and a coding principle of the population element (eligible solution of the problem)
2. A mechanism for generating the initial population
3. Operators allowing the population to cross and diversify :
   - `Selection` to define individuals who survive
   - `Crossing` recomposes the genes of two individuals previously selected
   - `Mutation` allows a better exploration of the space of solutions

Let’s say Pk the population at the first generation and N its size. We go from Pk to Pk+1 in three stages :

<p align="justify">
1. Selection: passage from Pk to Sk. The N individuals of Sk are selected (with possible repetition) among those of Pk according to their value. The others are dying
2. Crossing: passage from Sk to Ck. Two individuals (which will disappear: place for young people! ) cross to give birth to two children or crossing does not occur (and individuals remain unchanged). A constant probability is set crossing.
3. The possible mutation of the individuals obtained: passage from Ck to Pk+1. A constant probability of mutation is defined.
</p>

##### 4. Path to find a solution

<p align="justify">
In order to develop an effective approach, we first generated a random placement of all tasks and evaluated its cost. If, by chance, this total cost is below the threshold (given not to cross in order to ensure that the distribution of tasks on the multi-processor system is optimized), we return the placement made in the terminal. 
</p>

<p align="justify">
If necessary, we sort all the individuals of the population (= tasks) in ascending order and we keep some of them (say the least expensive 2/3) and, with the remaining 1/3, we merge them (crossing process) with individuals belonging to the 2/3, finally we change a task (mutation process) randomly on a processor. We repeat the operation indefinitely until reaching a sufficiently low total cost (in this case below the previously defined threshold). Thus, it is possible to make the choice to enlarge the population or to keep its initial size
</p>

##### References 

[[FR] Comprendre les algorithmes génétiques](https://igm.univ-mlv.fr/~dr/XPOSE2013/tleroux_genetic_algorithm/fonctionnement.html)

[[FR] Les Algorithmes génétiques](https://khayyam.developpez.com/articles/algo/genetic/)

[[EN] Introduction to Genetic Algorithms](https://link.springer.com/book/10.1007/978-3-540-73190-0)

[[EN] Genetic Algorithms | Stanford](https://link.springer.com/book/10.1007/978-3-540-73190-0](https://www-cs-students.stanford.edu/~jl/Essays/ga.html)https://www-cs-students.stanford.edu/~jl/Essays/ga.html)

