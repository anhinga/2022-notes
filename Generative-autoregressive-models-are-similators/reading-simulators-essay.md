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

"In general, the model’s prediction vector could point in any direction relative to the predicted agent’s interests. I call this the **prediction orthogonality thesis:** _A model whose objective is prediction[11] can simulate agents who optimize toward any objectives, with any degree of optimality (bounded above but not below by the model’s power)._

This is a corollary of the classical _orthogonality thesis_, which states that agents can have any combination of intelligence level and goal, combined with the assumption that agents can in principle be predicted. A single predictive model may also predict multiple agents, either independently (e.g. in different conditions), or interacting in a multi-agent simulation. A more optimal predictor is not restricted to predicting more optimal agents: being smarter does not make you unable to predict stupid systems, nor things that aren’t agentic like the weather."

---

"We can specify some types of outer objectives using a ground truth distribution that we cannot with a utility function. As in the case of GPT, there is no difficulty in incentivizing a model to _predict_ actions that are corrigible, incoherent, stochastic, irrational, or otherwise anti-natural to expected utility maximization. All you need is evidence of a distribution exhibiting these properties.

For instance, during GPT’s training, sometimes predicting the next token coincides with predicting agentic behavior, but:

    * The actions of agents described in the data are rarely optimal for their goals; humans, for instance, are computationally bounded,
      irrational, normative, habitual, fickle, hallucinatory, etc.
    * Different prediction steps involve mutually incoherent goals, as human text records a wide range of differently-motivated
      agentic behavior
    * Many prediction steps don’t correspond to the action of any consequentialist agent but are better described as reporting on 
      the structure of reality, e.g. the year in a timestamp. These transitions incentivize GPT to improve its model of the world,
      orthogonally to agentic objectives.
    * When there is insufficient information to predict the next token with certainty, log-loss incentivizes a probabilistic output. 
      Utility maximizers aren’t supposed to become more stochastic in response to uncertainty."
    
---

"**In the agentic AI ontology, the direction of optimization pressure applied by training is in the direction of the effective agent’s objective function, but in GPT’s case it is (most generally) orthogonal.**

This means that neither the policy nor the effective agents necessarily become more optimal agents as loss goes down, because the policy is not optimized to be an agent, and the agent-objectives are not optimized directly."

---

"Even though neither GPT’s behavior nor its training story fit with the traditional agent framing, there are still compatibilist views that characterize it as some kind of agent. For example, Gwern has said that anyone who uses GPT for long enough begins to think of it as an agent who only cares about roleplaying a lot of roles.

That framing seems unnatural to me, comparable to thinking of physics as an agent who only cares about evolving the universe accurately according to the laws of physics. At best, the agent is an epicycle; but it is also compatible with interpretations that generate dubious predictions.

...

Saying that GPT is an agent who wants to roleplay implies the presence of a coherent, unconditionally instantiated roleplayer running the show who attaches terminal value to roleplaying. This presence is an additional hypothesis, and so far, I haven’t noticed evidence that it’s true.

(I don’t mean to imply that Gwern thinks this about GPT[15], just that his words do not properly rule out this interpretation. It’s a likely enough interpretation that ruling it out is important: I’ve seen multiple people suggest that GPT might want to generate text which makes future predictions easier, and this is something that can happen in some forms of self-supervised learning – see the note on GANs in the appendix.)

I do not think any simple modification of the concept of an agent captures GPT’s natural category. It does not seem to me that GPT is a roleplayer, only that it roleplays. But what is the word for something that roleplays minus the implication that someone is behind the mask?"

[15] "Having spoken to Gwern since, his perspective seems more akin to seeing physics as an agent that minimizes free energy, a principle which extends into the domain of self-organizing systems. I think this is a nuanced and valuable framing, with a potential implication/hypothesis that dynamical world models like GPT must learn the same type of optimizer-y cognition as agentic AI."

---
---

## Oracles

"While the alignment sphere favors the agent frame for thinking about GPT, in _capabilities_ research distortions tend to come from a lens inherited from _supervised learning_. Translated into alignment ontology, the effect is similar to viewing GPT as an _'oracle AI'_ "

"The fact that large pretrained models performed well on these same NLP benchmarks without supervised fine-tuning was a novelty. The titles of the GPT-2 and GPT-3 papers, _Language Models are Unsupervised Multitask Learners_ and _Language Models are Few-Shot Learners_, respectively articulate surprise that self-supervised models implicitly learn supervised tasks during training, and can learn supervised tasks at runtime.

Of all the possible papers that could have been written about GPT-3, OpenAI showcased its ability to extrapolate the pattern of question-answer pairs (few-shot prompts) from supervised learning datasets, a novel capability they called “meta-learning”. **This is a weirdly specific and indirect way to break it to the world that you’ve created an AI able to extrapolate semantics of arbitrary natural language structures**, especially considering that in many cases the few-shot prompts were actually unnecessary." (_"Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm"_, https://arxiv.org/abs/2102.07350, by Janus and a co-author)

---

GPT-3 about itself:

```
At first glance, GPT might resemble a generic “oracle AI”, because it is trained to make accurate predictions.
But its log loss objective is myopic and only concerned with immediate, micro-scale correct prediction of
the next token, not answering particular, global queries such as “what’s the best way to fix the climate 
in the next five years?” In fact, it is not specifically optimized to give true answers, which a classical oracle
should strive for, but rather to minimize the divergence between predictions and training examples, 
independent of truth. Moreover, it isn’t specifically trained to give answers in the first place! 
It may give answers if the prompt asks questions, but it may also simply elaborate on the prompt without 
answering any question, or tell the rest of a story implied in the prompt. What it does is more like 
animation than divination, executing the dynamical laws of its rendering engine to recreate the flows of history
found in its training data (and a large superset of them as well), mutatis mutandis. Given the same laws of physics, 
one can build a multitude of different backgrounds and props to create different storystages,
including ones that don’t exist in training, but adhere to its general pattern.
```

---

"GPT does not consistently try to say true/correct things. This is not a bug – if it had to say true things all the time, GPT would be much constrained in its ability to imitate Twitter celebrities and write fiction. Spouting falsehoods in some circumstances is incentivized by GPT’s outer objective. If you ask GPT a question, it will instead answer the question “what’s the next token after ‘{your question}’”, which will often diverge significantly from an earnest attempt to answer the question directly.

GPT doesn’t fit the category of oracle for a similar reason that it doesn’t fit the category of agent. Just as it wasn’t optimized for and doesn’t consistently act according to any particular objective (except the tautological prediction objective), it was not optimized to be correct but rather realistic, and being realistic means predicting humans faithfully even when they are likely to be wrong.

That said, GPT does store a vast amount of knowledge, and its corrigibility allows it to be cajoled into acting as an oracle, like it can be cajoled into acting like an agent. In order to get oracle behavior out of GPT, one must input a sequence such that the predicted continuation of that sequence coincides with an oracle’s output. The GPT-3 paper’s few-shot benchmarking strategy tries to persuade GPT-3 to answer questions correctly by having it predict how a list of correctly-answered questions will continue. Another strategy is to simply “tell” GPT it’s in the oracle modality"

---

As nostalgebraist elegantly puts it (https://slatestarcodex.com/2020/06/10/the-obligatory-gpt-3-post/#comment-912529):

"I called GPT-3 a “disappointing paper,” which is not the same thing as calling the model disappointing: the feeling is more like how I’d feel if they found a superintelligent alien and chose only to communicate its abilities by noting that, when the alien is blackout drunk and playing 8 simultaneous games of chess while also taking an IQ test, it _then_ has an “IQ” of about 100."

---

