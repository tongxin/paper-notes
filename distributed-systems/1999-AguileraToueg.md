## A simple bivalency proof that t-resilient consensus requires t + 1 rounds

Authors: Marcos Kawazoe Aguilera and Sam Toueg

Publication: Information Processing Letters, 1999

Area: algorithm . consensus . crash failure . synchronous

This paper presents a new proof for the t+1 rounds lower bound in
achieving consensus among n processes with at most t crash failures.

Notations. A configuration is the collective state of all the processes.
A configuration C is 0-valent (or 1-valent) if starting from the
configuration the only possible decision value of the correct
processes is 0 (or 1). C is univalent if C is either 0-valent or
1-valent. Otherwise C is bivalent.

Assume there exists an algorithm that solves consensus in t
round. By this assumption the authors then present three lemmas, the
last one contradict with the first one.

Consider only executions where at most one process fails during each round.

Lemma 1: any t-1 round partial run results in a univalent
configuration.

Proof. Enumerate the last round runs by modifying only one message
from a faulty process at at time. Lets name this sequence l0, l1, ...
If r(t-1) is bivalent, then there must be two last round runs, li and
li+1, in which correct processes decide different values. However,
since li and li+1 only differs by one message, which affects at most
one correct process, some correct process can't distinguish between
them so it cannot decide different values in the two runs.

Lemma 2: there's a bivalent initial configuration.

Lemma 3: by induction, if k round partial run is bivalent, then k+1
round partial run is bivalent.

Proof. kind of trivial. 