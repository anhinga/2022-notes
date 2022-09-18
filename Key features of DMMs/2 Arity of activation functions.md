**It is crucial to be able to at least have input arity 2 for activation functions, because neurons which can multiply two linear combinations of their inputs are vital.**

But it is convenient to be able to have arbitrary input and output arity.

Typed DMMs tend to explicitly specify input and output arity of every type of neurons, and they also specify kinds of linear streams flowing through each input and output, see Section 2 of "Dataflow Matrix Machines and V-values: a Bridge between Programs and Neural Nets" <https://arxiv.org/abs/1712.07447>&#x20;

Untyped DMMs are using a single kind of linear streams sufficiently universal for a given situation. 
If this single kind of linear streams is based on V-values (see [Linear streams](1-Linear-streams.md)), 
then one can use variadic neurons with activation functions of unlimited arity, 
see Section 4 of "Dataflow Matrix Machines and V-values: a Bridge between Programs and Neural Nets" <https://arxiv.org/abs/1712.07447>
