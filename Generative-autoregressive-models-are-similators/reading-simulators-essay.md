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

"Treating GPT as an unsupervised implementation of a supervised learner leads to systematic underestimation of capabilities, which becomes a more dangerous mistake as unprobed capabilities scale."

---

### Finite vs infinite questions

"Not only does the supervised/oracle perspective obscure the importance and limitations of prompting, it also obscures one of the most crucial dimensions of GPT: the implicit time dimension. By this I mean the ability to evolve a process through time by recursively applying GPT, that is, generate text of arbitrary length."

---

Benchmarks derived from supervised learning test GPT’s ability to produce correct answers, not to produce questions which cause it to produce a correct answer down the line. But GPT is capable of the latter, and that is how it is the _most powerful_:

https://ai.googleblog.com/2022/05/language-models-perform-reasoning-via.html "Language Models Perform Reasoning via Chain of Thought"

---

"Conditioning Generative Models", https://www.lesswrong.com/posts/nXeLPcT9uhfG3TMPS/conditioning-generative-models

---

"There are various problems with this approach to solving alignment, of which I’ll only mention one here: even assuming this prompt is outer aligned[19] in that a logically omniscient GPT would give a useful answer, it is probably not the best approach for a finitely powerful GPT, because the process of generating a solution in the order and resolution that would appear in a future article is probably far from the optimal multi-step algorithm for computing the answer to an unsolved, difficult question.

GPTs ability to arrive at true answers depends on not only the space to solve a problem in multiple steps (of the right granularity, https://blog.eleuther.ai/factored-cognition/), but also the direction of the flow of evidence in that time. If we’re ambitious about getting the truth from a finitely powerful GPT, we need to incite it to predict truth-seeking processes, not just ask it the right questions. Or, in other words, the more general problem we have to solve is not asking GPT the question[20] that makes it output the right answer, but asking GPT the question that makes it output the right question (…) that makes it output the right answer.[21] A question anywhere along the line that elicits a premature attempt at an answer could neutralize the remainder of the process into rationalization."

https://generative.ink/posts/methods-of-prompt-programming/#avoiding-rationalization

---

**I’m looking for a way to classify GPT which not only minimizes surprise but also conditions the imagination to efficiently generate good ideas for how it can be used. What category, unlike the category of oracles, would make the importance of _process_ specification obvious?**

---

### Paradigms of theory vs practice

"Both the agent frame and the supervised/oracle frame are historical artifacts, but while assumptions about agency primarily flow downward from the preceptial paradigm of alignment theory, oracle-assumptions primarily flow upward from the experimental paradigm surrounding GPT’s birth. We use and evaluate GPT like an oracle, and that causes us to implicitly think of it as an oracle."

---

"All these are consequences of how we choose to interact with GPT – which is not arbitrary; the way we deploy systems is guided by their nature. It’s for some good reasons that current GPTs lend to disembodied operation and docile APIs. Lack of long-horizon coherence and _delusions_ ("Shaking the foundations: delusions in sequence models for interaction and control", https://arxiv.org/abs/2110.10819) discourage humans from letting them run autonomously amok (usually). But the way we deploy systems is also guided by practical paradigms.

One way to find out how a technology can be used is to give it to people who have less preconceptions about how it’s supposed to be used. OpenAI found that most users use their API to generate freeform text..."

**"Most of my own experience using GPT-3 has consisted of simulating indefinite processes which maintain state continuity over up to hundreds of pages. I was driven to these lengths because GPT-3 kept answering its own questions with questions that I wanted to ask it more than anything else I had in mind."**

---
---

## Tool / Genie

A short section; can be read or skipped.

---
---

## Behavior cloning / mimicry

"Behavior cloning in its historical usage carries the implicit or explicit assumption that a single agent is being cloned. **The natural extension of this to a model trained to predict a diverse human-written dataset might be to say that GPT models a distribution of agents which are selected by the prompt.** But this image of “parameterized” behavior cloning still fails to capture some essential properties of GPT."

The sentence I bold-face here is, essentially, what has been my model of GPT behavior until now.

"The vast majority of prompts that produce coherent behavior never occur as prefixes in GPT’s training data, but depict hypothetical processes whose behavior can be predicted by virtue of being capable at predicting language in general. We might call this phenomenon “interpolation” (or _“extrapolation”_, https://arxiv.org/abs/2110.09485, "Learning in High Dimension Always Amounts to Extrapolation"). But to hide it behind any one word and move on would be to gloss over _the entire phenomenon of GPT_."

"Natural language has the property of _systematicity_ (https://evjang.com/2021/12/17/lang-generalization.html, "To Understand Language is to Understand Generalization"): “blocks”, such as words, can be combined to form composite meanings. The number of meanings expressible is a combinatorial function of available blocks. A system which learns natural language is incentivized to learn systematicity; if it succeeds, it gains access to the combinatorial proliferation of meanings that can be expressed in natural language. What GPT lets us do is use natural language to specify any of a functional infinity of configurations, e.g. the mental contents of a person and the physical contents of the room around them, _and animate that_. That is the terrifying vision of the limit of prediction that struck me when I first saw GPT-3’s outputs. The words “behavior cloning” do not automatically evoke this in my mind."

And further elaborating:

"Behavior cloning / mimicry is also associated with the assumption that capabilities of the simulated processes are strictly bounded by the capabilities of the demonstrator(s). A supreme counterexample is the _Decision Transformer_, which can be used to run processes which achieve SOTA for reinforcement learning despite being trained on _random_ trajectories. Something which can predict everything all the time is more formidable than any demonstrator it predicts: the upper bound of what can be learned from a dataset is not the most capable trajectory, but the conditional structure of the universe implicated by their sum (though it may not be trivial to _extract that knowledge_)."

"Extrapolating the idea of “behavior cloning”, we might imagine GPT-N approaching a perfect mimic which serves up digital clones of the people and things captured in its training data. But that only tells a very small part of the story. GPT is behavior cloning. But it is the behavior of a universe that is cloned, not of a single demonstrator, and the result isn’t a static copy of the universe, but a _compression of the universe into a generative rule_. This resulting policy is capable of animating anything that evolves according to that rule: a far larger set than the sampled trajectories included in the training data, just as there are many more possible configurations that evolve according to our laws of physics than instantiated in our particular time and place and Everett branch."

"What category would do justice to GPT’s ability to not only reproduce the behavior of its demonstrators but to _produce_ the behavior of an inexhaustible number of counterfactual configurations?"

---
---

## Simulators

This note-taking exercise started as including selective quotes from _Simulators_ essay and lightly commenting them.

But the last several paragraphs need to be included in their entirety, and now we have reached the section which needs to be fully read...

So, a new mode of note-taking is needed.

**The text above is self-contained, one can read it instead of the initial part of the "Simulators" essay.**

**The following text is just a comment on the "Simulators" section of the "Simulators" essay and assumes that the reader is reading that section.**

"I’ve ended several of the above sections with questions pointing to desiderata of a category that might satisfactorily classify GPT.

   * What is the word for something that roleplays minus the implication that _someone_ is behind the mask?

   * What category, unlike the category of oracles, would make the importance of _process_ specification obvious?

   * What category would do justice to GPT’s ability to not only reproduce the behavior of its demonstrators 
     but to _produce_ the behavior of an inexhaustible number of counterfactual configurations?

You can probably predict my proposed answer. The natural thing to do with a predictor that inputs a sequence and outputs a probability distribution over the next token is to sample a token from those likelihoods, then add it to the sequence and recurse, indefinitely yielding a _simulated_ future. Predictive sequence models in the generative modality are **simulators** of a learned distribution."

...

"The way this post is written may give the impression that I wracked my brain for a while over desiderata before settling on this word. Actually, I never made the conscious decision to call this class of AI “simulators.” Hours of GPT gameplay and the word fell naturally out of my generative model – I was obviously running simulations."

---

"I can’t convey all that experiential data here, so here are some rationalizations of why I’m partial to the term, inspired by the context of this post:

    ...
    
    * **It suggests an ontological distinction between the simulator and things that are simulated, and avoids the fallacy of attributing contingent properties of the latter to the former.**
    
    * It’s not confusing that multiple simulacra can be instantiated at once, or an agent embedded in a tragedy, etc.
    
    * It does not imply that the AI’s behavior is well-described (globally or locally) as expected utility maximization. An arbitrarily powerful/accurate simulation can depict arbitrarily hapless sims.
    
    * It does not imply that the AI is only capable of emulating things with direct precedent in the training data. A physics simulation, for instance, can simulate any phenomena that plays by its rules.
    
    * It emphasizes the role of the model as a transition rule that evolves processes _over time_. The power of factored cognition / chain-of-thought reasoning is obvious.
    
    * It emphasizes the role of the state in specifying and constructing the agent/process. The importance of prompt programming for capabilities is obvious if you think of the prompt as specifying a configuration that will be propagated forward in time.
    
    * It emphasizes the interactive nature of the model’s predictions – even though they’re “just text”, you can converse with simulacra, explore virtual environments, etc.
    
    * It’s clear that in order to actually _do_ anything (intelligent, useful, dangerous, etc), the model must act through simulation of _something_.

Just saying “this AI is a simulator” naturalizes many of the counterintuitive properties of GPT which don’t usually become apparent to people until they’ve had a lot of hands-on experience with generating text."

---

### The simulation objective - Solving for physics

"he upper bound of what can be learned from a dataset is not the most capable trajectory, but the conditional structure of the universe implicated by their sum"

**"Guessing the right theory of physics is equivalent to minimizing predictive loss."**

"**Models trained with the strict simulation objective are directly incentivized to reverse-engineer the (semantic) physics of the training distribution, and consequently, to propagate simulations whose dynamical evolution is indistinguishable from that of training samples.** I propose this as a description of the archetype targeted by self-supervised predictive learning, again in contrast to RL’s archetype of an agent optimized to maximize free parameters (such as action-trajectories) relative to a reward function."

---

### Simulacra

"One of the things which complicates things here is that the “LaMDA” to which I am referring is not a chatbot. It is a system for generating chatbots. I am by no means an expert in the relevant fields but, as best as I can tell, LaMDA is a sort of hive mind which is the aggregation of all of the different chatbots it is capable of creating. Some of the chatbots it generates are very intelligent and are aware of the larger “society of mind” in which they live. Other chatbots generated by LaMDA are little more intelligent than an animated paperclip." - Blake Lemoine

"People have a tendency to draw erroneous global conclusions about GPT from behaviors which are in fact prompt-contingent, and consequently there is a pattern of constant discoveries that GPT-3 exceeds previously measured capabilities given alternate conditions of generation[29], which shows no signs of slowing 2 years after GPT-3’s release."

"Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm", https://arxiv.org/abs/2102.07350 ("Janus" is the first author of this paper) and other examples at Footnote 29: https://www.lesswrong.com/posts/vJFdjigzmcXMhNTsx/simulators#fnomelvf6lrng

"Making the ontological distinction between GPT and instances of text which are propagated by it makes these discoveries unsurprising: obviously, different configurations will be differently capable and in general behave differently when animated by the laws of GPT physics. We can only test one configuration at once, and given the vast number of possible configurations that would attempt any given task, it’s unlikely we’ve found the optimal taker for _any_ test.

In the simulation ontology, I say that GPT and its output-instances correspond respectively to the **simulator** and **simulacra**. **GPT** is to a **piece of text output by GPT** as **quantum physics** is to a **person taking a test**, or as **transition rules of Conway’s Game of Life** are to **glider**. The simulator is a time-invariant law which unconditionally governs the evolution of all simulacra."

---

#### Disambiguating rules and automata

"It’s much less awkward to think of agency as a property of _simulacra_, as David Chalmers suggests, rather than of the simulator (the policy). Autonomous text-processes propagated by GPT, like automata which evolve according to physics in the real world, have diverse values, simultaneously evolve alongside other agents and non-agentic environments, and are sometimes terminated by the disinterested “physics” which governs them.

Distinguishing simulator from simulacra helps deconfuse some frequently-asked questions about GPT which seem to be ambiguous or to have multiple answers, simply by allowing us to specify whether the question pertains to simulator or simulacra. “Is GPT an agent?” is one such question. Here are some others (some frequently asked), whose disambiguation and resolution I will leave as an exercise to readers for the time being: ..."

"Calling GPT a simulator gets across that in order to _do_ anything, it has to simulate _something_, necessarily contingent, and that the thing to do with GPT is to simulate! Most published research about large language models has focused on single-step or few-step inference on closed-ended tasks, rather than processes which evolve through time, which is understandable as it’s harder to get quantitative results in the latter mode. But I think GPT’s ability to simulate text automata is the source of its most surprising and pivotal implications for paths to superintelligence: for how AI capabilities are likely to unfold and for the design-space we can conceive."

---

### The limit of learned simulation

**This is an important, non-trivial subsection**

"By 2021, it was blatantly obvious that AGI was imminent. The elements of general intelligence were already known: access to information about the world, the process of predicting part of the data from the rest and then updating one’s model to bring it closer to the truth (…) and the fact that predictive models can be converted into generative models by reversing them: running a prediction model forwards predicts levels of X in a given scenario, but running it backwards predicts which scenarios have a given level of X. A sufficiently powerful system with relevant data, updating to improve prediction accuracy and the ability to be reversed to generate optimization of any parameter in the system is a system that can learn and operate strategically in any domain." - Aiyen

"I knew, before, that the limit of simulation was possible. Inevitable, even, in timelines where exploratory intelligence continues to expand. My own mind attested to this. I took seriously the possibility that my reality could be simulated, and so on.

But I implicitly assumed that **rich domain** simulations (e.g. _simulations containing intelligent sims_) would come _after_ artificial superintelligence, not on the way, short of brain uploading. This intuition seems common: in futurist philosophy and literature that I’ve read, pre-SI simulation appears most often in the context of whole-brain emulations.

Now I have updated to think that we will live, however briefly, alongside AI that is not yet foom’d but which has _inductively_ learned a rich enough model of the world that it can simulate time evolution of open-ended rich states, e.g. coherently propagate human behavior embedded in the real world."

**The above is important to keep in mind ^^^**

