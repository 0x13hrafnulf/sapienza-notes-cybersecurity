# Misc - Questions

- Explain how the fail-stop and the synchronous model are related
  - Fail-stop is less powerful than synchronous, because in synchronous we can solve clock-sync but not in Fail-stop; the set of problems solvable by Fail-stop are strictly contained in the set solvable by Synchronous
- We have seen that to implement a `(1,N)`-Atomic Register in fail-silent we need (at least) a majority of correct processes. However, the algorithm that uses `(1,N)`-Regular Registers does not need any failure detector, neither any assumption on correct majority. Could you argue on why is that?
  - The assumption of correct majority and the failure-detector are encapsulated inside the regular-register
- Is it a smart idea to set your clock to the average of your neighbors' clocks?
  - No, if we do not use other check and we just use the average of neighbors' we could set our clock to a past time
- Is it possible to implement a broadcast primitive that satisfies one of the following properties in a fail-stop systems with perfect p2p links:
  - If any process send a message `m`, then any other process delivers `m`
    - No is not possible, if a receiver crashes before the sending of the message this receiver will never deliver the message
  - If a correct process delivers `m`, then any other process delivers `m`
    - No is not possible, if a receiver crashes before the sending of the message this receiver will never deliver the message
- Show that any implementation of a Total Order Broadcast is sufficient to build a non-uniform consensus algorithm
  - Just run total order, everyone proposes a message and then thanks to total order a value is "elected"