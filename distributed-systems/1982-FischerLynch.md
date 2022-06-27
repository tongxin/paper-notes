
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

case k == 1. Prove no algorithm exists that solves interactive
consistency problem in 1 round given 1 actual fault. Construct a
sequence of executions, with the first outputing all zeros and the last
outputing all ones. The first execution and the last execution have no
faults. All the rest have one fault. The sequene of executions are
carefully arranged so that adjacent executions are indistinguishable
to some correct process, which implies that the consensus outputs of
all the executions should be the same. That contradicts the fact the
first and last executions output differently.

case k > 1. Reduce the case to 1-round consensus with input being the
the k-1 round output.

