# Reading "Simulators" by janus

https://www.lesswrong.com/posts/vJFdjigzmcXMhNTsx/simulators

The "Simulators" essay is written from the viewpoint of AI alignment/AI safety, and (as usual) the capability boost associated with
better understanding of Transformers and related models is an important aspect of the overall picture.

The two main topics of the essay are

  * Most alignment studies are rather out-of-date because the leading class of models, _generative autoregressive models created by self-supervised pretraining_, is very much unlike the previous leading classes of AI models;

  * _Generative autoregressive models created by self-supervised pretraining_ are **simulators**; one interacts not with these models themselves, but with **simulacra** they create.

This is mostly talking about Transformers driver by linguistic prompts, but the degree of generality of this consideration is `"models trained with predictive loss on a self-supervised dataset, invariant to architecture or data type (natural language, code, pixels, game states, etc)"`.

```
The outer objective of self-supervised learning is Bayes-optimal conditional inference over the prior of the training distribution,
which I call the simulation objective, because a conditional model can be used to simulate rollouts which probabilistically obey
its learned distribution by iteratively sampling from its posterior (predictions) and updating the condition (prompt). Analogously,
a predictive model of physics can be used to compute rollouts of phenomena in simulation. A goal-directed agent which evolves
according to physics can be simulated by the physics rule parameterized by an initial state, but the same rule could also propagate
agents with different values, or non-agentic phenomena like rocks. This ontological distinction between simulator (rule) and
simulacra (phenomena) applies directly to generative models like GPT.
```
