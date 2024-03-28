# Single-threaded
## malloc'd bufs
Fails the alignment check because heap allocations are not aligned you are
merely given a region in heap with the size you specified.

## memalign'd bufs
Aligning the heap to 8192 bytes solves the issue.

vim: set tw=80:
