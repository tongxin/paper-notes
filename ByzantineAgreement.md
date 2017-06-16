## Problems definitions

In distributed computing, reliably executing a protocol relies on the
capability of the whole system to act unanimously according to the
same state transition procedures despite a portion of the system may be
corrupted or compromised. How to make multiple parties to agree on the
same conclusion is the core issue to the reliability requirement. In
distributed computing theory, the agreement problems are framed in
three subtley different forms.

 - The consensus problem
 - The interactive consistency problem
 - The generals problems or reliable broadcast problem

### The consensus problem

Each process has an initial value xi. Some processes are
faulty. The consensus problem is about the existence and efficiency of
a protocol that renders every non-faulty process terminate with the
same decided value. Further properties are included to make the
problems non-trivial.

Properties:
 - Validity: the decided value must be one of the intially proposed values.
 - Weak agreement: no two non-faulty procesess decide on different values.
 - Strong agreement: no two processes decide on different values.
 - Termination: every non-faulty process decides.

The Validity and agreement properties are the safety properties of the
consensus problems. The termination properties are the liveness
properties. 

### The interactive consistency (IC) problem

The interactive consistency problem concerns for multiple processes
to agree on a vector of values in which the i'th element is nil or
proposed by the i'th process.

 - Validity: D is the decided vector then D[i] = xi or nil, xi being
   the value proposed by process i. Moreover, if process i is correct,
   then D[i] = xi
 - Agreement: no two processes decide on different vectors
 - Termination: non-faulty processes terminate

### The Byzantine generals problem

 - Validity: if leader is non-faulty, then all non-faulty processes
   decide on what it sent
 - Agreement: no two non-faulty processes decide on different values
 - Termination: every non-faulty process decides

### Relations between the three agreement problems

Multiplexing n instances of the generals problem with distinct
commanders provides a solution to the interactive consistency problem.
A solution to the IC problem can be easily adapted for consensus. 

## Important results

---
Theorem 1: There's no algorithm that solves interactive consistency
(or consensus) problem in a synchronous system of n processes, where
f processes are byzantine, when n <= 3f.
---

---
Theorem 2: 
---