## Subnetworks and modularization

See Section 8 "Network Topology" and Section 9 "Subnetworks and Modularization" of 
"Dataflow Matrix Machines and V-values: a Bridge between Programs and Neural Nets" https://arxiv.org/abs/1712.07447

The modern trend in artificial neural nets is to build the networks not from a
large number of single neurons, but from a relatively small number of modules
such as layers, etc.

In this sense, it is convenient that neurons in DMMs are powerful enough to
express the “up movement” action of whole subnetworks. This allows to build
DMMs from a relatively small number of powerful neurons, if so desired.

---

Pushing this further, one can always take a DMM network and wrap a super-neuron around it, enabling interesting hierarchies. 
It would be interesting to study situations where time flows faster in sub-networks inside super-neurons compared to the speed of the containing network.
