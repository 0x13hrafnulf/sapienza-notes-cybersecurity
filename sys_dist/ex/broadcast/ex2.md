# Broadcast - Exercise 2

## Text

Consider  the "All-Ack Uniform Reliable Broadcast" algorithm, what happens if the strong accuracy property of the perfect failure detector is violated? What if its strong completeness property is violated?

### Algorithm

```
// You broadcast a message, everyone who receives it start relaying and also start keeping track (in its personal memory) of the processes that have seen that message (through ack mechanism); when every correct process have seen the message I deliver it

upon event〈urb,Init〉do
  delivered:=∅;
  pending:=∅;
  correct:=Π;
  // Empty map, we use this to know who have seen the message m
  // If this is a super set of non-crashed processes then i can deliver the message because all the correct processes have seen it
  forall m do ack[m]:=∅;
  
upon event〈urb,Broadcast|m〉do
  pending:=pending ∪ {(self,m)};
  trigger〈beb,Broadcast|[DATA,self,m]〉;
  
upon event〈beb,Deliver|p,[DATA,s,m]〉do
  ack[m]:=ack[m] ∪ {p};  // If a process p is sending message m then p has seen m
  // If the message is not in pending then add it and start broadcasting (relay)
  if(s,m) !∈ pending then
    pending:=pending ∪ {(s,m)};
    trigger〈beb,Broadcast|[DATA,s,m]〉;

upon event〈P,Crash|p〉do
  correct:=correct - {p};
  
// Return true if correct processes are a subset of the processes that have seen the message
function candeliver(m) returns Boolean is
  return(correct ⊆ ack[m]);
  
upon exists(s,m) ∈ pending such that
    [candeliver(m)] ∧ [m !∈ delivered] do
  delivered:=delivered ∪ {m};
  trigger〈urb,Deliver|s,m〉;
```

## Solution

Strong accuracy but no strong completeness: if a process crash then is surely crashed but is possible that sometimes i don't know if someone crashes
  - The algorithm stops working because is possible that a process sends a message and you never deliver it because you wait for the ACK of someone who is dead

Strong completeness but no strong accuracy: every crash is detected but sometimes crashes could be false
  - The algorithm stops working because the agreement property is violated: someone will deliver a message that someone else will never deliver
  - This because someone's `candeliver()` function will return `true`, someone else' `false` 