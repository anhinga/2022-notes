# Reading _"Janus' GPT Wrangling"_ by Scott Alexander

https://astralcodexten.substack.com/p/janus-gpt-wrangling

Quoting the start of that essay:

```
Janus (pseudonym by request) works at AI alignment startup Conjecture. Their hobby, which is suspiciously similar to their work,
is getting GPT-3 to do interesting things.

For example, with the right prompts, you can get stories where the characters become gradually more aware that
they are characters being written by some sort of fiction engine, speculate on what’s going on, and sometimes even make
pretty good guesses about the nature of GPT-3 itself.
```

Then, after a **superimpressive quotation from GPT-3:** (read that quotation!)

```
How does it get this level of self-awareness? In this case, via rigged demo. Janus has developed Loom, 
a tool to write with GPT-3 more efficiently. It turns stories into branching trees where you can choose 
which of multiple completions to pick at any given point. 
```

Looking at "Loom: interface to the multiverse", https://generative.ink/posts/loom-interface-to-the-multiverse/

https://github.com/socketteer/loom

we notice that "janus" is the first author of these two papers:

"Multiversal views on language models", https://arxiv.org/abs/2102.06391

"Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm", https://arxiv.org/abs/2102.07350

---

'But sometimes GPT-3 genuinely gets it right. The most common way for that to happen is (again) by mistake. A common failure mode is to repeat the same sentence several times. GPT-3 was trained on a corpus of Internet text, and some of the Internet text was discussions of GPT-2. Many of the samples it saw that repeated the same sentence over and over in an endless loop were discussions of GPT-2 doing this. So sometimes it will get stuck in a loop, then end with “This is an example of text produced by a transformer language model”. This sounds like a stupid example from a Philosophy Of Self-Awareness class, but sometimes it really happens.'

'Instruct vs. Creative: The newest version of GPT-3 is called InstructGPT. It was trained with human feedback, ie it was “rewarded” for giving good answers and “punished” for giving bad ones, according to some combination of usefulness and political correctness. This has made it efficient, to-the-point, and boring.'

'Nobody trained GPT-3 to always respond 63 to random number queries. But something about making it give efficient, politically-correct answers to normal questions made it “choose” to “act” like it’s lower-temperature.'

'Cheerful AI: Janus tells me about a project at OpenAI to make GPT-3 happy and optimistic. They would run its responses through sentiment analysis and give it more reward when they detected more positive sentiment.

GPT-3 ended up deciding that the happiest thing it could think of was a wedding party, and that from now on it would only talk about wedding parties. Sometimes it would come up with natural transitions from your prompt to a wedding party scene. Once, it just used `***`, like a section break in a story, and started a “new chapter” which was a wedding party scene.'
