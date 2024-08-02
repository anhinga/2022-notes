# Grokking is (more or less) solved

The most interesting conceptual AI advances in recent months seem to come from "prosaic alignment" start-ups. 
These are companies which believe that the current trend of improving Transformer models is fairly likely to lead straight to AGI, 
and that better understanding of the nature and properties of these models is key to AI safety (and, of course, it's also key to better AI capabilities).

And it is often the case that the key elements of work are done by people "on the edge", "in the penumbra" of those alignment start-ups.

---

Recently the key new understanding of large Transformer models as simulators has emerged. 
That work has been done "while at Conjecture", but is not listed as directly coming from Conjecture 
(which is one of the "prosaic alignment" start-ups). 

I believe that the key people involved are still at Conjecture, but it looks like they feel it's
appropriate to keep some distance between Conjecture and this work. 

I am continuing to take notes of those materials here: [Generative autoregressive models are similators](../../../tree/main/Generative-autoregressive-models-are-similators)

---

Here is another one of those stories. Grokking is a phenomenon, where small Transformers look at a part of a mathematical structure for quite a while, 
and then rather suddenly transition to understanding the whole of that mathematical structure including the part they never see in training. 
It has been discovered in 2021 and has been a subject of a number of follow-up attempts to understand it. Here is my list of
Grokking-related literature: [Grokking](../../../tree/main/Grokking)

The recent breakthrough has been done in mid-August by Neel Nanda who left Anthropic (perhaps the most famous of the "prosaic alignment" start-ups) a few months ago. 
And it looks like he has more or less solved the mysteries behind this phenomenon. Here are the key relevant links:

https://www.neelnanda.io/blog/interlude-a-mechanistic-interpretability-analysis-of-grokking

https://twitter.com/NeelNanda5/status/1559060507524403200

https://www.alignmentforum.org/posts/N6WM6hs7RQMKDhYjB/a-mechanistic-interpretability-analysis-of-grokking

Highlights:

  * Deep relationship between grokking and phase changes
  * Grokking discovers an interpretable algorithms which uses discrete Fourier Transform and trigonometric identities
  * Circuits develop smoothly during training (the model interpolates between memorization and generalization, gradually shifting from pure memorization to pure generalization)

---

Neel Nanda wrote a number of other interesting things including
his recent take on the famous Anthropic paper he was involved in, "A Mathematical Framework for Transformer Circuits":

https://twitter.com/NeelNanda5/status/1580782930304978944

---

**January 2023:** There is now a paper, Neel Nanda et al., "Progress measures for grokking via mechanistic interpretability":

https://arxiv.org/abs/2301.05217

https://www.progress-measures-grokking.io/

---

**August 2024:** There is now a lot of literature on this. Here are two papers which seem particularly important:

"The Clock and the Pizza: Two Stories in Mechanistic Explanation of Neural Networks"

  * https://arxiv.org/abs/2306.17844 Ziqian Zhong, Ziming Liu, Max Tegmark, Jacob Andreas
  * https://openreview.net/forum?id=S5wmbQc1We NeurIPS 2023 oral
  * "Small changes to model hyperparameters and initializations can induce the discovery of qualitatively different algorithms from a fixed training set, and even parallel implementations of multiple such algorithms. Some networks trained to perform modular addition implement a familiar Clock algorithm; others implement a previously undescribed, less intuitive, but comprehensible procedure which we term the Pizza algorithm, or a variety of even more complex procedures. Our results show that even simple learning problems can admit a surprising diversity of solutions, motivating the development of new tools for characterizing the behavior of neural networks across their algorithmic phase space." 


