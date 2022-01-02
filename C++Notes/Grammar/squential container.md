# __Sequential Container__

## __Swap__

+ generally, swap is much faster than assigning since the former method does not copy, delete or insert any element indeed but just the inner data structure of two container except __array__.

+ as the result, after swap, pointers, references and iterators remain bound to the same element they denote before the swap except __string__.

## __insertion__

+ __array__ does not support any opration that change the size of container

+ __forward_list__ has its own __insert__ and __emplace__

+ 1. __insert( pos, n, val )__
+ 2. __insert( pos, begin, end )__
+ 3. __insert( pos, initializer )__

+ __KEY CONCEPTS : container elements are copies__

+ insert returns the iterator points to the first newly added elements.

+ __emplace_front, emplace, emplace_back__ correspond to __push_front, insert, push_back__
  
+ emplace pass arguments to the constructor of the elements type and construct an element directly in the space that managed by container avoiding copying operation.


## __Access__

+ __front(), back(), at()__ and __subscript__ return reference to the elements.

## __Remove__

+ removing any element but the first or last of a __deque__ invalidates all iterators, references and pointers.

+ as for __vector__ and __string__, it invalidate iterators, references and pointers after the erasure point only.

+ __erase__ return the iterator to the last element of the removed elements.
