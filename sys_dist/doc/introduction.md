# 0 - Introduction

- Distributed System
  - Definition
    - Set of entities, each of these with a certain computational power that are able to communicate and to coordinate among themselves
    - Spatially separated
    - Common goal
    - Fault tolerant
    - Very dynamic
  - Local view: a machine knows how the system is structured only if it can talk to the other machines of the system
  - Failures
    - Types
      - Detection (ex: checksum)
      - Masking (ex: redundancy and message retransmission)
      - Tolerance: if a machine stops working/doesn't work well the environment continue its execution
      - Recovery (ex: turn off and then turn on)
    - Failures are uncertain: we can't make our system work in every case, we must set a threshold (like: the system will work unless X machines stop working)
  - Simple agreement problem (Bizantine Generals)
    - First problem: message from A to B over unreliable channel (messages could be lost), even if we send an ACK for every message received we end up in and endless loop full of ACKs!
    - First solution: sync communications with a global clock so if a packet (and its ACK) doesn't arrive in X time this means this packet is lost (so we don't have to send infinite ACKs)
      - I think that here the three-way handshake kicks in
    - Second problem: global clock is impossible because clocks aren't precise and network creates unpredictable delays (asynchrony)
    - Second solution: we'll discover this during the course
- Methodology
  1. Model: specify the system in a formal way that abstract from the hardware
  2. Abstractions: "building blocks" of systems (formally defined) composed by specifications
  3. Specifications: "properties" which define abstractions and that must be respected
  4. Algorithms: pseudocode that runs on our model and do things to satisfy specifications of abstractions