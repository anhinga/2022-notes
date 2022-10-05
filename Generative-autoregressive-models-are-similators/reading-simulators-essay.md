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

---

Commenting the famous "The Unreasonable Effectiveness of Recurrent Neural Networks" by Karpathy (2015, 581 citations on Google Scholar at the moment):

```
Char-RNNs were like ouija boards, but actually possessed by a low-fidelity ghost summoned from a text corpus. 
I remember being thrilled by the occasional glimmers of semantic comprehension in a domain of unbounded constructive meaning.
```

And then commenting on https://www.gwern.net/GPT-3

```
Perhaps I could have started thinking several years earlier about what now seems so fantastically important. 
But it wasn’t until GPT-3, when I saw the qualitative correlate of “loss going down”, that I updated.
```

(Same here, but what convinced me was an example of competent Python code-generation from linguistic hints
in their famous demo: https://twitter.com/matvelloso/status/1263193089310461952)
