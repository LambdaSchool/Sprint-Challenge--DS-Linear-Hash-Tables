# Sprint Challenge: Hash Tables and Blockchain

In this week's Sprint you implemented some classic and fundamental data structures and learned about how to go about evaluating their respective runtimes and performance. We also learned how hash tables combine two data structures to get the best of both worlds.

This Sprint Challenge aims to assess your comfort with these topics through exercises that build on the data structures you implemented and the algorithmic intuition you've started to build up.

## Instructions

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This is an individual assessment. All work must be your own. Your challenge score is a measure of your ability to work independently using the material covered through this sprint. You need to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

You are not allowed to collaborate during the Sprint Challenge. However, you are encouraged to follow the twenty-minute rule and seek support from your PM and Instructor in your cohort help channel on Slack. Your work reflects your proficiency in Python and your command of the concepts and techniques in related to hash tables and blockchains.

You have three hours to complete this challenge. Plan your time accordingly.

## Commits

Commit your code regularly and meaningfully. This helps both you (in case you ever need to return to old code for any number of reasons and your project manager.

## Description

This sprint challenge is divided up into three parts:  Hash tables coding, blockchain coding, and a short interview covering parts of hash tables and blockchain.

## Project Set Up

#### [Hash Tables]

For the hash tables portion of the sprint challenge, you'll be working through two algorithm problems that are amenable to being solved efficiently using a hash table. You know the drill at this point. Navigate into each exercise's directory, read the instructions for the exercise laid out in the README, implement your solution in the .py skeleton file, then make sure your code passes the tests by running the test script with make tests.

A hash table implementation has been included for you already. Your task is to get the tests passing (using a hash table to do it). You can remind yourself of what hash table functions are available by looking at the hashtable.py file that is included in each exercise directory (note that the hash table implementations for both exercises differ slightly).

*You may not use any advanced, built-in Python functions to solve these problems.*

#### [Blockchain]

For the blockchain portion of the challenge, you will be writing code for a new miner that will solve a different Proof of Work algorithm than the one we have been working with.

Your goal is to mine at least one coin.  Keep in mind that with many people competing over the same coins, this may take a long time.  By our math, we expect that an average solution should be the first to find a solution at least once in an hour or two of mining.  

## Minimum Viable Product

#### Hash Tables

For the hash tables portion of the sprint challenge, you'll be working through some algorithm problems that are amenable to being solved efficiently using a hash table. You know the drill at this point. Navigate into each exercise's directory, read the instructions for the exercise laid out in the README, implement your solution in the `.py` skeleton file, then make sure your code passes the tests by running the test script with `-v`.

A hash table implementation has been included for you already. Your task is to get the tests passing by using hash table. You can remind yourself of what hash table functions are available by looking at the `hashtable.py` file that is included in each exercise directory (note that the hash table implementations for both exercises differ slightly). 

#### Implement a Ring Buffer Data Structure

A ring buffer is a non-growable buffer with a fixed size. When the ring buffer is full and a new element is inserted, the oldest element in the ring buffer is overwritten with the newest element. This kind of data structure is very useful for use cases such as storing logs and history information, where you typically want to store information up until it reaches a certain age, after which you don't care about it anymore and don't mind seeing it overwritten by newer data.

Implement this behavior in the RingBuffer class. RingBuffer has two methods, `append` and `get`. The `append` method adds elements to the buffer. The `get` method returns all of the elements in the buffer in a list in their given order. It should not return any `None` values in the list even if they are present in the ring buffer.

For example:

```python
buffer = RingBuffer(3)

buffer.get()   # should return []

buffer.append('a')
buffer.append('b')
buffer.append('c')

buffer.get()   # should return ['a', 'b', 'c']

# 'd' overwrites the oldest value in the ring buffer, which is 'a'
buffer.append('d')

buffer.get()   # should return ['d', 'b', 'c']

buffer.append('e')
buffer.append('f')

buffer.get()   # should return ['d', 'e', 'f']
```


#### Task 3. Reverse a Linked List

Inside of the `reverse` directory, you'll find a basic implementation of a Singly Linked List. _Without_ making it a Doubly Linked List (adding a tail attribute), complete the `reverse_list()` function within `reverse/reverse.py` reverse the contents of the list. 

For example,
```
1->2->3->None
```
would become...
```
3->2->1->None
```

While credit will be given for a functional solution, only optimal solutions will earn a ***3*** on this task.

#### Stretch 

* Say your code from `names.py` is to run on an embedded computer with very limited RAM. Because of this, memory is extremely constrained and you are only allowed to store names in arrays (i.e. Python lists). How would you go about optimizing the code under these conditions? Try it out and compare your solution to the original runtime. (If this solution is less efficient than your original solution, include both and label the stretch solution with a comment)

### Rubric

| OBJECTIVE                                                                                                                                         | TASK                                         | 1 \- DOES NOT MEET Expectations                                                                                              | 2 \- MEETS Expectations                                                                                                                                                                                                                      | 3 \- EXCEEDS Expectations                                                                                                                                                     | SCORE |
|---------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| \_Student should be able to construct a queue and stack and justify the decision to use a linked list instead of an array\.\_                     | Implement a Ring Buffer Data Structure       | Solution in ring\_buffer\.py DOES NOT run OR it runs but has multiple logical errors, failing 3 or more tests                | Solution in ring\_buffer\.py runs, but may have one or two logical errors\. Passes at least 7 of 9 tests                                                                                                                                     | Solution in ring\_buffer\.py has no syntax or logical errors and passes all tests                                                                                             |
| \_Student should be able to construct a linked list and compare the runtime of operations to an array to make the optimal choice between them\.\_ | Reverse the contents of a Singly Linked List | Student's solution in reverse\.py is failing one or more tests                                                               | Student's solution in reverse\.py is able to correctly print out the contents of the Linked List in reverse order, passing all tests, BUT, the runtime of their solution is not optimal \(requires looping through the list more than once\) | Student's solution in reverse\.py is able to correctly print out the contents of the Linked List in reverse order, passing all tests AND it has a runtime of O\(n\) or better |
| \_Student should be able to implement and describe how high\-level array functions work down to the memory level\_                                | Written Response                             | If you were evaluating this candidate for a position with your company, your would object to them being added to your team\. | If you were evaluating this candidate for a position with your company, you would be pleased to have this person on your team\.                                                                                                              | If you were evaluating this candidate for a position with your company, you would go out of your way to make sure this person is hired for your team\.                        |
| \_Student should be able to implement and utilize basic hash table \+ handle collisions and resizing in a hash table\_                            | Hash Problem 1                               | Tests do not pass, or solution does not use hash tables\.                                                                    | Tests pass\.  Solution utilizes a hash table\.                                                                                                                                                                                               | Tests pass with solutions utilizing hash tables, linear runtime complexity, no flake8 complaints\.                                                                            |
| \_Student should be able to implement and utilize basic hash table \+ handle collisions and resizing in a hash table\_                            | Hash Problem 2                               | Tests do not pass, or solution does not use hash tables\.                                                                    | Tests pass\.  Solution utilizes a hash table\.                                                                                                                                                                                               | Tests pass with solutions utilizing hash tables, linear runtime complexity, no flake8 complaints\.                                                                            |
