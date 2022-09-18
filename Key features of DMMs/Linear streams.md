**Linear streams are data streams which one can combine with numerical coefficients.**

We tend to use real numbers, but other numerical coefficients can also be used (e.g. complex).

We use the usual **linear combination of streams** terminology, but we don't insist on a particular set of axioms, we just want those operations of combining several streams with coefficients to be "reasonable in informal sense".

Examples:

- Streams of numbers
- Streams of vectors from a particular vector space
- Streams of images of a particular size (**animations**)
- Streams of matrices of a particular finite or countable size
- Streams of tensors of rank N of a particular finite or countable shape
- Streams of real-valued functions defined on set X
- Streams of signed measures defined over measurable space X
- Streams of signed samples from X (linear combination is computed as a stochastic sum; a sample is sampled from one of the constituent streams with probabilities determined by linear combination coefficients; so elements of X can be discrete; linear combination here is defined on streams, but does not need to be defined on the elements of X)
- Streams of formal finite linear combinations of elements of set X
- Streams of flexible tensors with tree-shapes indices (aka prefix trees with numerical leaves, aka nested dictionaries with numerical values, aka "tensors of mixed rank", aka "recurrent maps"). We call them **V-values** for vector-like-values. The theory of V-values is developed in Sections 3 and 5.3 of "Dataflow Matrix Machines and V-values: a Bridge between Programs and Neural Nets" <https://arxiv.org/abs/1712.07447> These days JAX **pytrees** can be used as a nice incarnation of V-values.

We tend to focus on finitely definable streams. For example, when we talk about matrices of countable size, we usually insist on those matrices having a finite number of non-zero elements at any given moment.

Using matrices of countable size with a finite number of non-zero elements at any given moment of time is a nice foundation for unbounded dynamically expanding networks (one just takes the network connectivity matrix to be a countable matrix with a finite number of non-zero elements at any given moment of time).

Tensors with a finite number of non-zero elements at any given moment of time is one nice way to provide a neural machine with unbounded memory. V-values is another way to do that.

This allows DMMs to be "naturally Turing complete". Standard constructions establishing Turing completeness of recurrent neural networks use artificial tricks such as real numbers of unlimited precision, abusing a binary expansion of a real number as a Turing machine tape and breaking the property of robustness to noise; this is why RNNs can't be used for general purpose programming, despite being "formally Turing complete". In the case of DMMs, their Turing completeness is "natural" and they can be used for stream-oriented programming.

A single DMM can use many kinds of linear streams at once (**typed DMMs**), or it can use a single kind of linear streams deemed sufficiently universal for a given class of tasks (the case of **untyped DMMs**).
