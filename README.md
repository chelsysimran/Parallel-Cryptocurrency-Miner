# Project 3: Parallel Cryptocurrency Miner

See instructions here: https://www.cs.usfca.edu/~mmalensek/cs220/assignments/project-3.html

## Written Responses

Edit this readme.md file to answer the following questions:

### Busy-waiting vs. Condition Variables

Once you have condition variables working in your program, compare the performance of busy waiting with condition variables. To ensure a fair comparison, use a single thread.

Report for the original program as well as modified version:

Total program run time:
Original Program: 1.77 seconds
Modified Program: 1.79 seconds
Hashes per second:
Original Program: 565595.77 hashes/second
Modified Program: 577779.25 hashes/second
CPU usage during execution (use the top command to get a rough estimate of the average CPU usage):
Original Program: 113.4
Modified Program: 110.7


Which version performs better? Is this the result you expected? Why or why not?

The Modified program performs better. This was the result I expected because as went over in class, this program was parallelizable, and computationally intensive. A parallelized program distributes different tasks to multiple worker threads, and in our case doing so would benefit the performance (in comparison to the serial version). I did expect the numbers to be very far off in terms of proximity, but it makes sense in terms of the fact that we’re using mutex locks to ensure thread safety - which also slows down the program. (((but mostly because Professor Matthew said so in class!!)))

### Nonces Per Task

Experiment with different values for `NONCES_PER_TASK`. What value yields the best performance in terms of hashes per second on your machine?

1000000 Nonces per Task yields the best result in terms of hashes/second.
1000000 hashes in 0.07s (15336056.13 hashes/sec)

### Performance I

When evaluating parallel programs, we use speedup and efficiency. Why are these metrics not as useful when measuring the performance of our parallel crytocurrency miner?

These metrics are not as useful when we are measuring the efficiency of our parallel cryptocurrency miner because we are using critical sections and locking them with mutexes, for the ‘safety’ of the threads. This therefore doesn’t allow for taking efficiency and speedup into consideration, because in this case it would actually slow our program down.

### Performance II

Using any of the `kudlick` machines (in our 220 classroom), what is the highest performance you were able to achieve in terms of hashes per second? What configuration did you use (`NONCES_PER_TASK`, number of threads, block data, compiler options)?

The Highest performance we were able to achieve in terms of hashes per second was:
582436

The configuration we were using was:
NONCES_PER_TASK: 1000000
Number of threads: 4
Block data: Hello CS 220!!!
Compiler Options: - 

