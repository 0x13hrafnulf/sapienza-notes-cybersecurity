# Shared memories - Exercise 6

## Text

Explain why the request identifier included in `WRITE,ACK,READ,VALUE` messages of the "Majority Voting" algorithm can be omitted in the "Read-One Write-All" algorithm

![](../../res/img/179.png)

## Solution

Because in "Read-One Write All" for each write you wait all the ACKs, so every write operation is serialized; it's not possible that there are pending writes on the channel. When you start a new write you know that all the messages of the previous write are no more on the channel.

In "Majority Voting" we don't wait for all the ACKs because we need just a quorum of ACKs so a timestamp is necessary; for example if a message `m` containing a write operation is very slow and a quorum of processes replies to the other write messages (`m1,m2...`) then the write message `m` (if we don't use timestamps) could affect the future state of the system.