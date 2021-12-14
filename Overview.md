## Course Theme: Abstraction Is Good But Don’t Forget Reality
- These abstractions have limits Especially in the presence of bugs
- Foundation of computer systems underlying principles for hardware, software, and networking

### GreatReality  #1: Ints   are   not   Integers,   Floats   are   not   Reals
Example   1:   Is   $x^2 ≥ 0$?
- Float’s:   Yes!
- Int’s: Not always. *range of 32-bit int is -2147484648 to 2147483648. (2e9)*

```
(lldb) print 50000*50000
(int) $0 = -1794967296
```

Example   2:   Is   $(x + y) + z = x + (y + z)$?
- Unsigned   &   Signed   Int’s:   Yes!
- Float’s: Not always. 

### Great Reality #2: You’ve Got to Know Assembly
- Understanding assembly is key to machine-level execution model.
- Understanding optimizations done or not done by the compiler helps to Tuning program performance.

### Great Reality #3: Memory Matters Random Access Memory Is an Unphysical Abstraction
- Memory referencing bugs especially pernicious
	- Out of bounds array references
	- Invalid pointer values
	- Abuses if malloc and free
- Memory performance is not uniform, and cache and virtual memory effects can greatly affect program performance

### Great Reality #4: There's more to performance than asymptotic complexity
- Even exact op count does not predict performance
- Measure program performance and identify bottlenecks.

>  ![[MemoryAccessPatterns.png]]
> different memory access patterns of copy a 2048 * 2048 matrix

### Great Reality #5: Computer do more than execute programs
- I/O system get data in and out, which critical to program reliability and performance.
- Communication with each other over networks


## 7 Labs are the heart and soul of the course
- [Lab Assignments](http://csapp.cs.cmu.edu/3e/labs.html)

##  Amdahl's Law
- When we speed up one part of a system, the effect on the overall system performance depends on both how significant this part was and how much it sped up.

- Some part of a system requires a fraction $a$, and its performance improved by a factor of $k$. The speedup $S = \frac{1}{(1-a) + a/k}$ 
- Considering the effect of setting $k$ to $\infty$, We get $S_{\infty} = \frac{1}{1-a}$ . There is a limitation of overall improvement by speed a part of system up.
- To significantly speedup the entire system, we must improve the speed of a very large fraction of  the overall system.
