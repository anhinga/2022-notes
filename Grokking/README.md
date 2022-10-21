# Grokking resources

**Note: it looks like Grokking has been mostly solved by Neel Nanda in August 2022: [Grokking is solved](../../../tree/main/Grokking-is-solved)**

---

Here are some Grokking resources:

The original paper: "Grokking: Generalization Beyond Overfitting on Small Algorithmic Datasets", https://arxiv.org/abs/2201.02177

First published at MATH-AI, ICLR 2021 workshop: https://mathai-iclr.github.io/papers/papers/MATHAI_29_paper.pdf

"Hypothesis: gradient descent prefers general circuits", by Quintin Pope, 
https://www.lesswrong.com/posts/JFibrXBewkSDmixuo/hypothesis-gradient-descent-prefers-general-circuits

Independent implementation (PyTorch), and independently measured learning curves: https://github.com/teddykoker/grokking

See also "Building agents that know how to experiment, by training on procedurally generated games", by Robin Shah,
and more specifically https://www.lesswrong.com/posts/zvWqPmQasssaAWkrj/an-159-building-agents-that-know-how-to-experiment-by#DEEP_LEARNING_

---

The original "Grokking" paper has 22 citations at Google Scholar at the moment:

https://scholar.google.com/scholar?cites=4466239674951044045

A number of those citations are follow-up studies directed towards understanding the phenomenon of "Grokking".

Let's specifically note:

"The Slingshot Mechanism: An Empirical Study of Adaptive Optimizers and the Grokking Phenomenon", https://arxiv.org/abs/2206.04817
(from Apple, Machine Learning Research: https://machinelearning.apple.com/research/slingshot-mechanism)

"Towards Understanding Grokking: An Effective Theory of Representation Learning", https://arxiv.org/abs/2205.10343 (with Max Tegmark)

"Multi-scale Feature Learning Dynamics: Insights for Double Descent", https://arxiv.org/abs/2112.03215 (with Yoshua Bengio)

"Hidden Progress in Deep Learning: SGD Learns Parities Near the Computational Limit", https://arxiv.org/abs/2207.08799 (with Boaz Barak)

---
---
---

Historic note (I don't think this is directly relevant, but let's keep it to document the train of thoughts):

"The DMM training setup is presumably a perfect setup for Grokking (precise capture of simple tasks
by moderately sized models). However, it is not clear how easy or difficult it would be to get there
with our current DMM setup (by the standards Grokking research, in terms of the number of training steps
and such, we certainly have not tried nearly hard enough yet)."

I am not sure at the moment whether the preliminary observations of some remarkable generalization effects during DMM synthesis 
are related to phenomena observed during Grokking run (https://github.com/anhinga/DMM-synthesis-lab-journal/blob/main/history.md)



