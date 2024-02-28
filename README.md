# List-Queue-Implementation

This repository contains a simple implementation of a queue data structure in C++.

Description
The code consists of a queue class that implements basic queue operations such as enqueue, dequeue, front, and print. The queue is implemented using a singly linked list.

Code Overview
Structure Definition (slistEl):
Defines a structure slistEl representing a node in the linked list. Each node contains a pointer to the next node (next) and an integer value (data).

Queue Class (queue):
Implements a queue data structure using a singly linked list.
Member variables:
head: Points to the first element in the queue.
tail: Points to the last element in the queue.
Member functions:
queue(): Constructor to initialize the queue.
~queue(): Destructor to deallocate memory.
empty(): Checks if the queue is empty.
front(): Returns the front element of the queue.
enqueue(int v): Inserts a new element at the end of the queue.
dequeue(): Removes the front element from the queue.
print(): Prints all elements in the queue.

Main Function (main()):
Creates a queue object Q.
Generates 10 random integers and enqueues them into the queue.
Prints the queue and the front element.
Dequeues two elements from the queue, prints the queue and the front element, and enqueues a new random integer.
Repeats the dequeue/enqueue process for a total of 10 iterations.
Dequeues the remaining elements from the queue and prints the queue.

How to Use
To use this code:
Clone the repository to your local machine.
Compile the C++ code using a C++ compiler.
Run the compiled executable.
