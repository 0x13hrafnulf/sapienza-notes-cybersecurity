# Misc - Exercise 5

## Text

Consider the following leader election algorithm executed by a correct process based on reliable broadcast and consensus. The system is formed by `N` processes, at most `f` can fail by crashing and at most `b` can misexecute line `(*)` by sending any different value from the outcome of the consensus.
1. Write `COND` in the algorithm
2. What is the relation among `N`, `f` and `b`? 

```
// Code of process ID

INIT
  candidate[j]=null for each j
  leader=null
  propose(ID)

upon decide(x)
  RBsend(x) to all  // (*)

upon RBreceive(y) from pj
  candidate[j]=y

when (COND)
  leader=select most frequent ID from candidate
```

## Solution

1. COND: in `candidate[]` we have a value that has frequency `b+1` and is not `null`
2. Exercise 2
  - `f` must be `0`: we don't have a perfect FD so if the leader crashes we can not elect a new leader
  - `N > 2b`: for this `leader=select most frequent ID from candidate`
    - `N-b >= b+1` so `N >= 2b+1`