## CACHE SIM
<!-- forse e' denoted by e non denoted with -->
* Main Memory M with n cells, an element is denoted with M[i] with $0 \leq i < n$
* Cache C of $k \ll n$ cells, an element is denoted with C[i] with $0 \leq i < k$
* $l$ as i understand is a sequence of indices and every an element is denoted with
    $l_{j}$ for $j$ = 1, 2, ..., and such that every $l_{j} \in [0, n-1]$
    The j-th access to the main memory is denoted with M[$l_{j}$]
# Functioning
If the cell M[$l_{j}] **IS** stored in C then simply access the element
Otherwise:
    * If C has an empty cell place M[$l_{j}] in the lowest indexed free cell of C and then access it
    * Else select a cell to evict with eviction policy, store M[$l_{j}] in the cell that was chosen to be evicted and then access the element

# Eviction Policies
* **LRU (Least Recently Used)**: evict the cell whose latest access lies farthest in the past
* **HASH**: evict cell C[$(l_{j}$ mod p $)$ mod $k$] with $p = 2^{19-1} = 524287$ <!--(mersenne prime lesgo) -->
Note that accesses that fill an empty cell of C are caches misses

# Input-Output Specs
* Input:
    * Assume that $n = 2^{31}$
    * Command Line specs(in order):
        1. path to the file with the indices of access' requests, one index per row
        2. cache size k
* Output:
    * Number of access requests handled
    * Number of cache misses of LRU
    * Number of cache misses of HASH
    * **IF $k \leq 20** for each policy print in the order LRU, HASH the indices of main memory cells stored in C, print one index per row and -1 if a cell is empty. As i understand only at the end of the whole sequence and not after every insertion

# Grading
I'm goated so i should reach the efficiency requirement. 1 min etc, etc, ... . It should be o(k), doesn't seem right, maybe O(k) but I'll see
# Watch Out
Program must be written in **cacheSim.java**, with a public class called **cacheSim**. Write at the start of the program a comment explaining the data structures used and the main ideas, also if you used AI but I don't want to use it.
No package declaration. (does it mean no other packages? I shouldn't create my own packages?) what does it mean
Only allowed packages are java.lang, java.io, and java.util. (Maybe i just shouldn't write it explictly)
I must submit only the program file, is that the .java or the .class? Can i split into multiple files
