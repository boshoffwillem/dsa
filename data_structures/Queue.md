# Queue

Queue follows the First In First Out (FIFO) rule - the item that goes in first
is the item that comes out first.

## Basic Operations of Queue

A queue is an object (an abstract data structure - ADT) that allows
the following operations:

- **Enqueue**: Add an element to the end of the queue
- **Dequeue**: Remove an element from the front of the queue
- **IsEmpty**: Check if the queue is empty
- **IsFull**: Check if the queue is full
- **Peek**: Get the value of the front of the queue without removing it

## Working of Queue

Queue operations work as follows:

- two pointers `FRONT` and `REAR`
- `FRONT` track the first element of the queue
- `REAR` track the last element of the queue
- initially, set value of `FRONT` and `REAR` to -1

### Enqueue Operation

- check if the queue is full
- for the first element, set the value of `FRONT` to 0
- increase the `REAR` index by 1
- add the new element in the position pointed to by `REAR`

### Dequeue Operation

- check if the queue is empty
- return the value pointed by `FRONT`
- increase the `FRONT` index by 1
- for the last element, reset the values of `FRONT` and `REAR` to -1

## Complexity Analysis

The complexity of enqueue and dequeue operations in a queue using an array is `O(1)`.

## Applications of Queue

- CPU scheduling, Disk Scheduling
- When data is transferred asynchronously between two processes.
The queue is used for synchronization. For example: IO Buffers, pipes, file IO, etc
- Handling of interrupts in real-time systems.
- Call Center phone systems use Queues to hold people calling them in order.

## Types of Queues

There are four different types of queues:

- Simple Queue
- Circular Queue
- Priority Queue
- Double Ended Queue

### Simple Queue

In a simple queue, insertion takes place at the rear and removal occurs at
the front. It strictly follows the FIFO (First in First out) rule.

### Circular Queue

In a circular queue, the last element points to the first element
making a circular link.
The main advantage of a circular queue over a simple queue is better
memory utilization. If the last position is full and the first position
is empty, we can insert an element in the first position.
This action is not possible in a simple queue.

### Priority Queue

A priority queue is a special type of queue in which each element
is associated with a priority and is served according to its priority.
If elements with the same priority occur, they are served according
to their order in the queue.
Insertion occurs based on the arrival of the values and removal occurs based on priority.
Priority queue can be implemented using an array, a linked list,
a heap data structure, or a binary search tree. Among these data structures,
heap data structure provides an efficient implementation of priority queues.

### Deque (Double Ended Queue)

In a double ended queue, insertion and removal of elements can be performed from
either from the front or rear. Thus, it does not follow the
FIFO (First In First Out) rule.
