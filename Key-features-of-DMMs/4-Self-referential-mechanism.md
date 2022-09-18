**There is a variety of ways to create self-referential mechanisms in this framework.**

Here I present one possible way we have developed in detail and experimented with.

Neural machines work by repeating a two-stroke cycle. The inner mechanisms of neurons work during the first phase of the cycle. Then the network connectivity matrix remixes the neuron outputs with weights and creates neuron inputs for the next cycle during the second phase of the cycle.

To allow the neural machine to modify its own connectivity matrix, we create a dedicated neuron *Self* which emits a new network connectivity matrix on each step during the first phase of each cycle (or it might emit a more complex structure which contains the connectivity matrix; this can also be implemented incrementally for efficiency reasons if the implementation uses immutable streams). This newly created connectivity matrix is used during the second phase of the same cycle.

The newly created connectivity matrix is just one of the neuron outputs, so along with other neuron outputs it gets remixed during the second phase to create neuron inputs for the next cycle.

This allows the network to analyze its own connectivity and to use its own connectivity structure in various ways, in addition to using it directly during the second phase of a two-stroke cycle.

A tutorial is here: [2021 self transforming neural machines tutorial](https://github.com/anhinga/2021-notes/tree/main/self-transforming-neural-machines/tutorial)


We used this self-referential mechanism in our open-source experiments to

- produce controlled wave patterns in the network matrix
- create randomly initialized self-referential DMMs obtaining interesting emerging behaviors
- edit a running network on the fly by sending it requests to edit itself (in particular, this enables live-coding, but this is also quite open-ended, since it enables a population of networks to tell each other to modify themselves; of course, the receiving network doesn’t have to follow an incoming instruction to self-modify blindly, although in the most simple-minded case it would do so)
