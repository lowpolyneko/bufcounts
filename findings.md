# Single-threaded
## malloc'd bufs
Fails the alignment check because heap allocations are not aligned you are
merely given a region in heap with the size you specified.

## memalign'd bufs
Aligning the heap to 8192 bytes solves the issue. Increases performance by ~2
ns.

Before the bufs were packed together with the item struct which include some
additional elements that hugely boost the size of the total struct. Heap
allocating the buffers greatly increases the cache locality of both the buffer
array and the item array.


vim: set tw=80:
