# __Shared Pointer__

+ __new__ allocate memory for an object and return a pointer

+ __delete__ receive a pointer and desctruct the object it points to and free the linked memory

## method that both __shared_ptr__ and __unique_ptr__ suppport

1. shared_ptr\<T> sp / unique_ptr\<T> up

2. p

3. *p

4. p->mem       equals to (*p).mem

5. p.get()      return the pointer saved in p

6. swap(p, q)

7. p.swap(q)

## method thar only __shared_ptr__ owns

1. make_shared\<T> (args) args is used to initialize the object

2. shared_ptr\<T> p(q) p is a copy of q, this opration will increase the counter of q

3. p = q

4. p.unique() return true if p.use_count = 1

5. p.use_count() return the number of smart pointers that share the same object with p
