# Misc - Exercise 3

## Text

You have a client that communicates with a server. The server stores a number `x` (initially `1`), and the client is able to send the following operations:
- `MUL(Y)`: updates `X` on the server with `X*Y`
- `GET()`: returns the value `X` on the server

The client is connected with a link that does not lose messages and it has the following timed delivery property:
- A message sent at time `t` is received by at most `t+d`

The behavior of the client is the following, it first issues a burst of `MUL` operations and then after `3d` times units retrieves `X` from the server, then after other `3d` units another cycle happens. Consider only link algorithms.
1. What algorithm would you use taking into account that you want to minimize the overhead introduced?
2. What algorithm would you use if `X` and `Y` are not numbers but matrices?

## Solution

1. No additional algorithm has to be used
   - The link does not lose messages: each message has to be sent exactly once and it  will be received
   - The link may deliver messages out of order but the multiplicative operation is commutative; once the burst ends, after `2d` time units at most, the server received all the updates and it will store the same value that would have stored if it received operations in order
2. In this case we have to build a `FIFO` channel over the link: matrix multiplication is not commutative