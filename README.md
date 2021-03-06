
- **Description:**

Using an existing Java Checkers program with an AI player against a human player, we optimized the runtime of multiple test scenarios through multithreading. The alpha-beta process of finding the best and worst possible moves was improved via multithreading. We ran and compared the running time for both the original unthreaded checkers game and then the modified multithreaded checkers program. Our findings showed that the implementation of the multithreading to the the alpha-beta process decreased the running time, thus improving the efficiency.

- **Documentation of Project:**

https://docs.google.com/document/d/1KsT_fNUPJ5mDhNA4n1FqL7stfrzGQ6OCryoyVkByDfo/edit?usp=sharing

- **Process:**

Naturally Alpha-beta is not a parallelizable algorithm because each parent node depends on the calculation of their child node. So our approach to the parallel implementation of the checkers game divides the search tree and spreads it across several threads. In alpha-beta, each branch of the tree is evaluated independent of other branches. The master thread takes cares of the following:

1. Getting all the possible moves
2. Spawning N threads, where N is the number of possible moves.
3. Have each thread calculate the cost of each move using the alpha-beta pruning algorithm.
4. Return the best move based on the highest cost calculated.


- **Results:**

###### Running program in a MacBook Pro 2012, Processor: 2.5 Ghz Intel Core i5

Original Code with Running Time of Alpha-Beta Decision: 972 ms
![alt text](https://github.com/cristyevr94/Checkers/blob/master/Original-Mac.PNG)

Multithreaded Code with Running Time of Alpha-Beta Decision: 537 ms
![alt text](https://github.com/cristyevr94/Checkers/blob/master/Multithreaded-Mac.PNG)

###### Running program in a Dell Inspiron 7559, Processor: Intel(R) Core(TM) i7-6700HQ CPU @ 2.60GHz and a Nvidia GeForce GTX 960M Video Card.

Original Code with Running Time of Alpha-Beta Decision: 420 ms
![alt text](https://github.com/cristyevr94/Checkers/blob/master/Original-Dell.PNG)

Multithreaded Code with Running Time of Alpha-Beta Decision: 240 ms
![alt text](https://github.com/cristyevr94/Checkers/blob/master/Multithreaded-Dell.PNG)

- **Conclusion:**

The improvement with multithreading shows how to improve games and programs by decreasing their total time to process. Multithreading shows us the benefit of having several sequential instructions running simultaneously. It clearly showed that while running alpha-beta in one thread, as compared to several different threads, the total time to process a move was decreased significantly. In the future we can examine looking at the NegaMax algorithm and its implementation. NegaMax, is another gaming algorithm, which succeeds where the MiniMax algorithm fails [5]. In later implementations, it would be prudent to  reconsider this implementation and see if a multithreaded approach can be improved upon as well.

### To see changes from original code look at files:
- Game.java
- Robot.java


# - Instructions from Original Code:

Checkers game made as part of Artificial Intelligence course at IIT Ropar.

Allowed Modes:

1) Human vs Human
2) Human vs Computer
3) Computer vs Computer

To run follow these steps.

Step 1: Compile the source code
javac checkers/*.java

Step 2: Run the main class
java checkers/Checkers

In the computer vs computer mode the game results in a draw since each player
plays optimally. Therefore the game goes on indefinitely. The user needs to
manually kill the game to stop it.
