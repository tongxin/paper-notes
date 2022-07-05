## The Deep Learning Compiler: A Comprehensive Survey

https://dblp.org/rec/journals/corr/abs-2002-03794.html

As of mid 2022, this paper is still the go-to paper to get
a glimpse of the whole area, covering the relevant materials fairly
thoroughly unless the reader is looking for some particularly recent
development.

The survey organization follows the usual front-end back-end
dichotomy, where the front-end is centered around high level IRs and
the the back-end focused on low level IRs. The high level IRs are
all in certain forms of graph representation, e.g., DAG, let-bindings,
and special tensor-based notations. On graph IR implementation,
techniques pertaining to data representation such as dynamic shape,
data layout, and special operator types
such as broadcast, control flow, and derivatives, are discussed.

The low level IRs present fine-grained representations that enable
hardware dependent optimization and managing direct memory accesses.
The paper categorized low level IRs into three types: Halide-based IRs,
Polyhedral-based IRs and other types of IR. MLIR was put in the third
category as it was only in its early stage of development.

Front end optimizations feature algebraic simplication, operator fusion,
DCE, CSE, static memory planning, layout optimization and so on.

A list of back end optimizations are discussed: hardware intrinsic mapping, memory
allocation and data fetching, memory latency hiding, loop scheduling,
parallelization methods and several autotuning techniques.

The paper was published in early 2020. It's fair to believe that many
technical topics covered in this paper need to be updated.


## RAMMER: Enabling Holistic Deep Learning Compiler Optimizations with rTasks

https://dblp.org/rec/conf/osdi/MaXYXMCHYZZ20.html

The key observation is neural network parallelisms are normally exploited
separately on two levels which are inter-operator and intra-operator.

Two issues exist that hamper the two level scheduling scheme from achieving
optimal performance. The first issue is kernel launching overhead.
The second is lack of intra-operator parallelism.

To solve the problems, Rammer first breaks operators into smaller sized 
rTasks, which are fine grained and ideally minimum schedulable software 
units. Then it groups rTasks into a series of rPrograms, each emitted to
the accelerator for running. The key role of Rammer compiler is processing
the rTask-based DAG graph and planning output rPrograms against vEUs, which
are an abstraction of underlying accelerator execution units. The mapping
from vEU to the hardware is carried out at run time.

A program is organized as a two dimensional array of rTasks, with each
row mapped to a virtual device. Then Rammer relies on scheduling heuristics
to schedule the rTask graph on its wavefronts.

Scheduling interface is straigntforward: Append to append an rTask to a
virtual execution unit, Wait to exert task dependences.

The rKernels can either be hand-tuned or automatically generated.

That said, this work is positioned at one level higher than a kernel
generating compiler, such as TVM.

