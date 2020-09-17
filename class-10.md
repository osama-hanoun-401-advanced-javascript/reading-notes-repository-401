# Stacks and Queues

## Stacks

### What's a Stack?!

* A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

* Common terminology for a stack is:
  * Push - Nodes or items that are put into the stack are pushed
    * Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.
    * When adding a Node, you push it into the stack by assigning it as the new top, with its next property equal to the original top.
    
  * Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
    * Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.
    * Typically, you would check isEmpty before conducting a pop. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.
    
  * Top - This is the top of the stack.

  * Peek - When you peek you will view the value of the top Node in the stack. When you 
    attempt to peek an empty stack an exception will be raised.
    * When conducting a peek, you will only be inspecting the top Node of the stack.
    * Typically, you would check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.
    * We do not re-assign the next property when we peek because we want to keep the reference to the next Node in the stack. This will allow the top to stay the top until we decide to pop.

  * IsEmpty - returns true when stack is empty otherwise returns false.
    * Do a check for the top value if it doesn't exist **Null** then the stack is empty.

## Queue

### What's a Queue?!

* Adata structure in which nodes are removed in the same order they were entered. This is often referred to as FIFO (first in, first out). 

* Common terminology for a queue is:
  * Enqueue - Nodes or items that are added to the queue.
    * When you add an item to a queue, you use the enqueue action. This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

  * Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
    * When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.
    * Typically, you would check isEmpty before conducting a dequeue. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

  * Front - This is the front/first Node of the queue.

  * Rear - This is the rear/last Node of the queue.

  * Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
    * When conducting a peek, you will only be inspecting the front Node of the queue.
    * Typically, you want to check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.
    We do not re-assign the next property when we peek because we want to keep the reference to the next Node in the queue. This will allow the front to stay in the front until we decide to dequeue

  * IsEmpty - returns true when queue is empty otherwise returns false.
    * Do a check for the front value if it doesn't exist **Null** then the stack is empty.




