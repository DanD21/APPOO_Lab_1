#Game of Life

##Struct Class

There is a structure with 3 integer fields - row, col, value, and a print function that you will consider that is unused for the entire program, but it was very useful for testing. It's role is to save elements that will be modified after a step is finished. Every time an element should be modified I push a structure in a stack with it's position and value. I created it because in java you don't have implemented a structure class, or maybe there is one but I'm too lazy to search it. 

##GoL Class

Here there is a list of lists of integers. In this list, line by line it reads and add data from input file. It is using lists because it will be easier to add new elements or to delete than in case with arrays, where it should work with memory allocation. So it works like an infinte grid. 

*bounds function*

On every step it check bounds on left right up and down and search for live cells, in this case for 1. If it founds an 1 then it adds 2 line of 0's on that side. To avoid out of index errors.

*step function*

Here are applied the rules for the live and dead cells using some loops. Every time it needs to make a change in grid it makes a struct object and push it in stack. After it processes the entire list, it applies changes from stack.

*unbound function*

After a step the live cells may move, and leave after them a lot of free unused space, and there is a function that will delete unused space. Unused space is considered all lines that are made only from zeros, on all bounds. That gives a good performance when something that moves is used as seed. 

##Performance

It works really fast in cases when seeds are used like slider or blinker, where it moves but don't leaves live cells after it, 2.8 - 4.7 seconds for 1 000 000 steps. Unfortunately, for bigger is still working but performance is lower as bigger is grid.



