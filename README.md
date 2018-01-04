# ios-glossary
A single page for all iOS related jargons

## Memory

### Stack: 
This is the fastest way to read and write variables for the compiler. There is one private stack per thread. Threads share information through the heap. When we enter into a new scope (declared with "{ }" in Objective-C), the compiler makes space for it in the stack, when this scope ends (returning from a function or getting in to the close bracket), the compiler releases all the space allocated in the stack for that scope by returning the stack pointer back to the previous position into the parent’s scope. As a result, there is no way to retain objects allocated in the stack: the object(s) will be released when the scope ends no matter what you do.

### Heap: 
It is unique per application and it shared between all threads. It is a simple structure where you put objects that will never be released unless you (or ARC) do it manually. It is slower than the stack but there are many advantages: it can request more space if it needs it (if a stack runs out of space your app will crash with a stackoverflow exception), and you can delete any object without affecting another (in the stack this is not possible, since you push and pop things in a specific order).

Reference - [Blocks and Memory Management (Stack vs Heap) Written by Pablo Alcalde](https://www.solstice.com/blog/blocks-and-memory-management-stack-vs-heap)

