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

---

"In retrospect, an exploration of the _limits_ of language modeling should have read something more like:

```
If loss keeps going down on the test set, in the limit – putting aside whether the current paradigm can approach it – 
the model must be learning to interpret and predict all patterns represented in language, including 
common-sense reasoning, goal-directed optimization, and deployment of the sum of recorded human knowledge. 
Its outputs would behave as intelligent entities in their own right. You could converse with it by alternately generating 
and adding your responses to its prompt, and it would pass the Turing test. In fact, you could condition it to generate 
interactive and autonomous versions of any real or fictional person who has been recorded in the training corpus
or even _could_ be recorded (in the sense that the record counterfactually “could be” in the test set). 
Oh shit, and it could write code…
```
"

"I don’t know of any explicit discussion of this limit predating GPT, except a working consensus of Wikipedia editors that NLU is AI-complete."

---

https://www.lesswrong.com/posts/YJRb6wRHp7k39v69n/implications-of-gpt-2

```
I was impressed by GPT-2, to the point where I wouldn’t be surprised if a future version of it could be used pivotally using
existing protocols.

Consider generating half of a Turing test transcript, the other half being supplied by a human judge. 
If this passes, we could immediately implement an HCH of AI safety researchers solving the problem if it’s within our reach at all. 
(Note that training the model takes much more compute than generating text.)

This might not be the first pivotal application of language models that becomes possible as they get stronger.

It’s a source of superintelligence that doesn’t automatically run into utility maximizers. It sure doesn’t look like AI services,
lumpy or no.
```

---
---

## Agents

David Chalmers lucidly observed that the policy’s relation to agents is like that of a “chameleon” or “engine”:

```
GPT-3 does not look much like an agent. It does not seem to have goals or preferences beyond completing text,
for example. It is more like a chameleon that can take the shape of many different agents. 
Or perhaps it is an engine that can be used under the hood to drive many agents. But it is then perhaps these systems 
that we should assess for agency, consciousness, and so on.
```

https://dailynous.com/2020/07/30/philosophers-gpt-3/#chalmers

---

### Fluid ephemeral agents

"Presently, GPT is the only way to instantiate agentic AI that behaves capably outside toy domains. These intelligences exhibit goal-directedness; they can plan; they can form and test hypotheses; they can persuade and be persuaded. It would not be very dignified of us to gloss over the sudden arrival of artificial agents _often indistinguishable from human intelligence_ just because the policy that generates them “only cares about predicting the next word”.

But nor should we ignore the fact that these agentic entities exist in an unconventional relationship to the policy, the neural network “GPT” that was trained to minimize log-loss on a dataset. GPT-driven agents are ephemeral – they can spontaneously disappear if the scene in the text changes and be replaced by different spontaneously generated agents. They can exist in parallel, e.g. in a story with multiple agentic characters in the same scene. There is a clear sense in which the network doesn’t “want” what the things that it simulates want, seeing as it would be just as willing to simulate an agent with opposite goals, or throw up obstacles which foil a character’s intentions for the sake of the story. The more you think about it, the more fluid and intractable it all becomes. Fictional characters act agentically, but they’re at least implicitly puppeteered by a virtual author who has orthogonal intentions of their own. Don’t let me get into the fact that all these layers of “intentionality” operate largely in [indeterminate superpositions](https://generative.ink/posts/language-models-are-multiverse-generators/#multiplicity-of-pasts-presents-and-futures)."

The last link is in https://generative.ink/posts/language-models-are-multiverse-generators/

---
