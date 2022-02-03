# Distributed Systems

## Disclaimer

"Receive (and send) is the interface between the protocol layer and the underlying network channels. Deliver is the interface between the protocol layer and the application. It is thus a naming convention to make it easy to distinguish message arrival at different layers, instead of having to say "received at the protocol" (aka received) and "received at the application" (aka delivered)."

So delivered != received but sometimes in the summary i'll put in brackets near deliver "receive" (ex: the process `p` delivers (receives) message `m`...); this just to remember that delivering a message implies the receiving

## Index

### Theory

- [0 - Introduction](./doc/introduction.md)
- [1 - Models, Abstractions, and Basic Concepts](./doc/models_abstractions_and_basic_concepts/model-abstractions-and-basic-concepts.md)
- [2 - Time in Distributed Systems](./doc/time-in-distributed-systems/time-in-distributed-systems.md)
- [3 - Basic Broadcast Primitives](./doc/basic_broadcast_primitives/basic-broadcast-primitives.md)
- [4 - Shared Memories](./doc/shared_memories/shared-memories.md)
- [5 - Consensus](./doc/consensus/consensus.md)
- [6 - Total Ordering and Replicated State Machine](./doc/total_ordering_and_replicated_state_machine/total-ordering-and-replicated-state-machine.md)
- [7 - BFT (Byzantine fault tolerant)](./doc/bft/bft.md)
- [8 - Blockchains](./doc/blockchains/blockchains.md)

### Exercises

- Time
  - [Exercise 1](./ex/time/ex1.md): considering a pseudocode and links that are not FIFO, show that (Mutual Exclusions) doesn't hold
  - [Exercise 2](./ex/time/ex2.md): an algorithm has the immediate delivery property if it immediately delivers the messages received to the upper layer, apply this property to the Perfect point2point FIFO algorithm
  - [Exercise 3](./ex/time/ex3.md): does this algorithm implements an eventual FD?
  - [Exercise 4](./ex/time/ex4.md): implement a perfect failure detector given an algorithm
- Broadcast
  - [Exercise 1](./ex/broadcast/ex1.md): modify the "Lazy Reliable Broadcast" algorithm to reduce the number of messages sent in case of `k` failures (with `k < n`) to `O(k*n)`
  - [Exercise 2](./ex/broadcast/ex2.md): consider  the "All-Ack Uniform Reliable Broadcast" algorithm, what happens if the strong accuracy property of the perfect failure detector is violated? What if its strong completeness property is violated?
  - [Exercise 3](./ex/broadcast/ex3.md): can we design a uniform reliable broadcast algorithm with an eventually perfect failure detector but without assuming a majority of correct processes?
  - [Exercise 4](./ex/broadcast/ex4.md): compare the causal delivery property with the following property (Ex 3.11): "If a process delivers messages `m1` and `m2`, and `m1→m2`, then the process must deliver `m1` before `m2`"
  - [Exercise 5](./ex/broadcast/ex5.md): can we design a best-effort broadcast algorithm that satisfies the causal delivery property without being a causal broadcast algorithm (without satisfying the agreement property of a reliable broadcast)?
  - [Exercise 6](./ex/broadcast/ex6.md): synchronous/asynchronous channels and crash with leader election
  - [Exercise 7](./ex/broadcast/ex7.md): provide all the delivery sequences after instant `t` such that causal order is satisfied
  - [Exercise 8](./ex/broadcast/ex8.md): provide all the possible sequences satisfying Causal Order and complete the execution in order to have a run satisfying FIFO order but not causal order
  - [Exercise 9](./ex/broadcast/ex9.md): execution completing
- Shared memories
  - [Exercise 1](./ex/shared_memories/ex1.md): regular and atomic execution analysis
  - [Exercise 2](./ex/shared_memories/ex2.md): regular and atomic execution analysis
  - [Exercise 3](./ex/shared_memories/ex3.md): could you show how to simulate message passing using a (1,1)-atomic registers?
  - [Exercise 4](./ex/shared_memories/ex4.md): regular and atomic execution analysis
  - [Exercise 5](./ex/shared_memories/ex5.md): give an algorithm that implements a `(1,1)` atomic register in the fail-silent model and that is more efficient than the "Read-Impose Write-Majority" algorithm which implements a `(1,N)` atomic register in the fail-silent model
  - [Exercise 6](./ex/shared_memories/ex6.md): explain why the request identifier included in `WRITE,ACK,READ,VALUE` messages of the "Majority Voting" algorithm can be omitted in the "Read-One Write-All" algorithm
  - [Exercise 7](./ex/shared_memories/ex7.md): regular and atomic execution analysis
  - [Exercise 8](./ex/shared_memories/ex8.md): regular and atomic execution analysis
- Misc
  - [Questions](./ex/misc/questions.md)
  - [Exercise 1](./ex/misc/ex1.md): algorithm designing
  - [Exercise 2](./ex/misc/ex2.md): algorithm designing
  - [Exercise 3](./ex/misc/ex3.md): algorithm designing
  - [Exercise 4](./ex/misc/ex4.md): logically instantaneous concept
  - [Exercise 5](./ex/misc/ex5.md): complete the algorithm
  - [Exercise 6](./ex/misc/ex6.md): algorithm designing
- Consensus
  - [Exercise 1](./ex/consensus/ex1.md): in Paxos, suppose that a cluster contains `5` servers and `3` of them have accepted proposal `6` with value `X`. Once this has happened, is it possible that **any** (at least one) server in the cluster could accept a different value `Y`?
  - [Exercise 2](./ex/consensus/ex2.md): in Paxos, suppose we let each participant timestamps its prepare requests with the pair `(ID, ts)` (where `ts` is an increasing counter), and we use the following rule `(ID',ts') > (ID, ts)` if `ID'>ID` or (`ID'=ID` and `ts'>ts`); discuss if the properties of safety and liveness are impacted
- Total ordering
  - [Exercise 1](./ex/total_ordering/ex1.md): implement the total order broadcast in a system where processes are "aligned" and there is an oracle that handles failures reconnecting the "line" of processes
  - [Exercise 2](./ex/total_ordering/ex2.md): show that any implementation of TO is sufficient to create a (non fault-tolerant) mutual exclusion algorithm. How would you modify your algorithm to have a fault-tolerant mutual exclusion algorithm given the `P` failure detector?
- Software replication
  - [Exercise 1](./ex/software_replication/ex1.md): is this a valid Raft configuration?
- Exams
  - [December 4th](./ex/exams/dec-4.pdf) - Simulation 
