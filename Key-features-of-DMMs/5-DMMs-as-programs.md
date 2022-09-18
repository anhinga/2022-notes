## DMMs as continuously deformable programs

We can think of a space with unlimited ambient supply of silent neurons with every kind of possible activation function, and we can consider countable connectivity matrices with finite number of non-zero elements (the infinite silent network with finite active part), and continuous deformations of those matrices are continuous deformations of the corresponding programs.

Our explorations of various programming exercises in this formalism seem to indicate that it is likely to be adequate as a high-level general purpose programming formalism in dataflow or functional reactive style of stream-oriented programming. See [Map of DMM-related programming examples and techniques](https://github.com/anhinga/2020-notes/tree/master/programming-overview) 
linked from https://anhinga.github.io/.

---

The dimension of the network and the dimension of data are decoupled, so compact neural machines for solving conventional programming problems are available. 

For example, by considering streams of maps from words to numbers, one can build a dataflow matrix machine counting words in a given text which uses only a few neurons. 

Similarly, by considering streams of V-values (flexible tensors based on tree-shaped indices) and embedding of lists into trees, one can build a similarly compact dataflow matrix machine accumulating a list of asynchronous incoming events.

## Program Synthesis

This formalism has a strong potential for novel methods of program synthesis. We hope to make this potential a reality in near future.

The task of synthesis of dataflow matrix machines should be more tractable than conventional program synthesis. 
When one works with DMMs, the task of learning program sketches is reformulated as *neural architecture search*, and converting a program sketch to a full program should be done by conventional methods of neural net training.

Dataflow matrix machines allow us to combine

  * aspects of *program synthesis* setup (compact, human-readable programs);
  * aspects of *program inference* setup (continuous models defined by matrices).
