

## Authenticated Algorithms for Byzantine Agreement

Authors: D. Dolev, H. Strong

Publication: SIAM Journal on Computing, 1983

Area: algorithm . byzantine agreement . synchronous . authenticated

An algorithm is presented that solves Byzantine agreement
(consensus) problem in t + 1 rounds with O(n^2) messaging complexity,
where no more than t processes are faulty. A modifed version is given
with t + 2 rounds and O(tn) total messages.

```
Theorem(LSP): Byzantine agreement problem with authentication can be
achieved for n processes with at most t faults within t + 1 rounds,
assuming n > t + 1.
```

Proof sketch:

In round r, each process appends its signature to the received message
and sends the message to all those processes that haven't signed it.
The messages correspond to distinct paths starting from the first
signer to the last signer. The commander may be equivocal by sending
different values to different recipients. In round t, each valid
message that includes t distinct signatures either has already been seen 
by a good process, which means it'll let the value known by all the
good processes in the next round, or the message will be sent to a
good process by the end of round t, then get propagated to all good
processes by the end of round t+1. It's possible that some proposed
values may not reach any correct process at all. But it's guaranteed
that all correct processes will have seen the same set of proposed
values by the end of round t+1.

```
Theroem 2: Byzantine agreement cannot be achieved for n processes with
within t or fewer rounds, where t is the number of faults and n > t+1
```

Proof sketch:

Define an equivalence relation among all the execution histories. Say,
S $\sim$ T if S and T is indistinguishable to some reliable process
p, that is, p receives the same messages and behaves the same in both
S and T. The proof strategy then is to construct a sequence of t-round
executions s0, s1, ... sk such that s0 and sk have different consensus
values while s0 $\sim$ s1 ... $\sim$ sk. 

```
Theorem 3: Byzantine agreement can be achieved within t rounds using
O(n^2) messages.
```

Construction. At round i, each process totally orders all the messages
received during previous round. A processor only relays at most two
messages about the first two distinct values it has not see before, to
receivers which haven't signed over the values.  Each correct process
sends at most two messages over each edge. If a correct process
receives (v)-signed by p1, p2 ... pt+1, with v first time seen, then
it's clear that p1 through pt are all faulty so pt+1 must be correct.
The correct pt+1 means all the other correct processes should have
received the same message.

```
Theorem 4: Byzantine agreement can be achieved within t+2 rounds
using O(nt) messages.
```

Select t+1 processes as dedicated relayers.

```
Theorem 5: Byzantine agreement can be achieved on a complete network
within t+1 rounds using O(nt) messages.
```

When n >= 2t+1, Choose 2t+1 processes to be active and let the others
be passive.

