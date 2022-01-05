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

## __Special forward_list__

+ __forward_list__ can't access precessor so it has __insert_after, emplace_after, erase_after__ instead of __insert, emplace, erase__.

## __Iterator Invalidation__

+ iterators, pointers, and references to a __vector__ or __string__ are invalid if the container was reallocated. If no reallocation happens, indirect references to elements before the insertion remain valid; those to elements after the insertion are invalid.

+ for __deque__, if we add at the front or back, iterators are invalidated, but references and pointers to existing elements are not.

+ If we remove elements at the back of the __deque__, the off-the-end iterator is invalidated but other iterators, references, and pointers are unaffected; they are also unaffected if we remove from the front.

+ for __vector__ and __string__, The off-the-end iterator is always invalidated when we remove elements.

## __Capacity Management__

+ If the requested size is greater than the current capacity, reserve allocates __at least as much as__ (and may allocate more than) the requested amount.

+ If the requested size is less than or equal to the existing capacity, __reserve does nothing.__

+ We can call __shrink_to_fit__ to ask that memory beyond what is needed for the current size be returned to the system, __but calling shrink_to_fit is only a request__; there is no guarantee that the library will return the memory.

> __Each vector implementation can choose its own allocation strategy. However, it must not allocate new memory until it is forced to do so.__

## __Adapter__

+ By default both __stack__ and __queue__ are implemented in terms of __deque__, and a __priority_queue__ is implemented on a __vector__. We can override the default container type by naming a sequential container as a second type argument when we create the adaptor:  
`stack<string, vector<string>>`

+ __priority_queue__ requires __random access__ in addition to the front, push_back, and pop_back operations; it can be built on a __vector__ or a __deque__ but __not on a list__.

+ The __queue__ adaptor requires back, push_back, front, and push_front, so it can be built on a __list__ or __deque__ but __not on a vector__.
