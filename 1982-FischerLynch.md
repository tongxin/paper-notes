
## A Lower Bound for the Time to Assure Interactive Consistency

Authors: Michael J. Fischer and Nancy A. Lynch

Publication: Information Processing Letters, 1982

Area: algorithm . interactive consistency . synchronous . unauthenticated

This paper proves the round lower bound for interactive consistency
problem in a synchronous system of n processes in which k processes
are actually byzantine, provided k <= t, where t is maximum byzantine
faults allowed for achieving interactive consistency, which is known
to require 3t < n. 

Proof idea:
Consider k round consensus problems as a function F(s, p, r) over
execution histories, recursing on the result produced over k - 1
rounds. Now change the execution by modifying a message sent from a
byzantine process in round k. Assuming k round consensus solution
exists, then there exists 1-round consensus function tolerating 1
faulty process. Now allow kth byzantine process fail in round k.
By applying the 1-round consensus protocol, a sufficient condition
for achieving k round consensus is the k-1 round output established a
consensus. This can be easily achieved by applying the algorithm over
the first k-1 rounds given k-1 failures. 
