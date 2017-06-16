

## Authenticated Algorithms for Byzantine Agreement

Authors: D. Dolev, H. Strong

Journal: SIAM Journal on Computing, 1983

In this paper is presented an algorithm that solves Byzantine agreement
(consensus) problem in t + 1 rounds with O(n^2) messaging complexity,
where no more than t processes are faulty. A modifed version is given
with t + 2 rounds and O(tn) total messages.

Theorem(LSP): Byzantine agreement problem with authentication can be
achieved for n processes with at most t faults within t + 1 rounds,
assuming n > t + 1.

Proof sketch:

In round r, each process appends its signature to the received message
and sends the message to all those processes that haven't signed it.
The messages correspond to distinct paths starting from the first
signer to the last signer. The commander may be equivocal by sending
different values to different processes. In round t, each valid
message that includes t distinct signatures either has already been seen 
by a good process, which means it'll let the value known by all the
good processes. Or the message will be sent to a good process by the
end of round t, then get propagated to all good processes by the end
of round t+1. It's possible that some proposed values may not be known
by good processes at all. But it's guaranteed that all good processes
will have seen the same set of proposed values by the end of round
t+1.


