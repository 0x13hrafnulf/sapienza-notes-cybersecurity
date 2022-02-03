# Time - Exercise 2

## Text

An algorithm has the immediate delivery property if it immediately delivers the messages received to the upper layer (not considering the negligible local computational time of an handler)

```
upon event Init
  Pending:=∅ // Messages that have been received but are out of order
  seq:=0 // Sequence number of the messages
  del_seq:=0 // Sequence number of the last message delivered

upon event Send fl(〈pd,m〉) // pd = process destination
  Send perfect(pd,< m,seq >)
  seq=seq+1
  
// Every time i deliver a message i add this to the Pending set
upon event Delivery from perfect(〈ps,< m,seq >〉) // ps = process source
  Pending=Pending ∪ {〈ps,< m,seq >〉}

// (4)
// Triggered if in Pending set exists a message that has send_seq = del_seq
upon event ∃〈ps,< m,send_seq >〉∈ Pending such that send_seq=del_seq
  Delivery FL(ps,m) 
  Pending=Pending-{〈ps,< m,send_seq >〉}
  del_seq=del_seq+1
```

The Perfect point2point FIFO code you have seen above does not have this property (we are using `Pending` set)

As a matter of fact is possible that a message stays in the `Pending` set for an unpredictable amount of time before being delivered
- Can you implement (on top of a perfect channel) a version of FIFO that has the immediate delivery property?
- Show the pseudocode and a description
- Discuss the pros and cons of the normal FIFO algorithm and the one with immediate delivery
- Prove formally that your algorithm respect FIFO

## Solution

Yes, i simply send message `1`, then message `2` (that contains also message `1`, [`1`,`2`]) etc... so i'll never loose a message and even if it happens then i'll restore it in the next receive

We can also do that the receiver sends ACKs so for example if process `p0` sends `5` messages to process `p1` and `p1` answer with an ACK to the fifth message then `p0` will start another "window" of messages and won't include in this window messages from `1` to `5` because they have been ACKed

- Pros: messages shouldn't be resent
- Cons: messages could become very long

Formally the algorithm respects FIFO because there isn't a pending set, messages just arrive in order

### Pseudocode

(Made by me so it could be wrong)

```
upon event Init
  Sent:=∅ // Messages that have been sent
  seq:=0 // Sequence number of the messages
  del_seq:=-1 // Sequence number of the last message delivered

upon event Send fl(〈pd,m〉) // pd = process destination
  Sent = Sent ∪ {< m,seq >}
  Send perfect(pd,Sent)
  seq=seq+1
  
upon event Delivery from perfect(〈ps,Recv〉) // ps = process source
  Delivery FL(ps,Recv - {...Recv[del_seq]})
  del_seq=max(send_seq(Recv))
```