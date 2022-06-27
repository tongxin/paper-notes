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
 
