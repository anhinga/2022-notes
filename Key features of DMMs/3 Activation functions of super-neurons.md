**A wide range of activation functions transforming linear streams is possible.**

On one end, standard simple activation functions like identity and coordinate-wise ReLU are available. On the other end of complexity, a super-neuron can wrap any piece of software as long as the input and output communications are via linear streams.

We have also experimented with activation functions containing asynchronous communication channels (especially for the external input); then the absence of signal in the asynchronous queue at a given clock tick is interpreted as zero vector.
