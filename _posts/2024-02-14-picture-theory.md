---
title: "LLM and Wittgenstein's picture theory"
# date: 2024-02-14
permalink: /posts/picture-theory/
# tags:
#   - cool posts
#   - category1
#   - category2
---

These are some unconcluded thoughts that seem worth writing down.

## 1. On AGI and Language

Recently, artificial intelligence can roughly be divided into three categories:

- **Computer Vision**: This refers to AI technology related to image and video processing.
- **Natural Language Processing**: This refers to AI technology related to human language.
- **Audio Processing**: This refers to AI technology related to voice and sound.

All three fields are advancing at a terrifyingly fast pace. AI is rapidly conquering vision, hearing, and even language. In fact, multimodal technologies, which span across these areas, are also evolving. For example, AI can now turn text into images or describe the contents of images through text.

This got me thinking: when it comes to achieving AGI, artificial general intelligence that surpasses human intelligence, which of these three technologies is the most important? Is vision important, or is hearing more important, or perhaps language? I believe it's language. Why? Because language is the fundamental tool humans use to understand the world.


## 2. Wittgenstein's Picture Theory

To explain this, there's nothing better than Wittgenstein's Picture Theory. According to the Picture Theory, **"the structure of the world parallels the structure of language."** 

Let me give a simple example. Imagine there's news about a car accident (just making this up):

*"Last Monday afternoon, a car accident occurred on Melrose St., LA. According to the police, the accident started when a sedan overtook another vehicle in the first lane. The car attempting to overtake suddenly braked hard, and the following vehicle couldn't avoid the collision. Although both cars were seriously damaged, fortunately, there were no casualties. The drivers sustained minor injuries and received first aid at the scene."*

Even though we didn’t witness the accident firsthand, we can still roughly understand the situation. This is because language paints a picture of the accident scene.

Conversely, if we only saw a video of the accident and didn’t read the text, we could still grasp the situation. Some might argue that this disproves the idea that "language is the tool for understanding the world." But the argument still holds. We recognize the video as an accident because we see the cars crashing, and the fact that "the cars crashed" cannot be defined without language. Even though I may not consciously think of the exact words "the cars crashed" when I picture the scene in my mind, it’s clear that we cannot process this without the tool of language. (I hope this gives you at least a rough idea of what I'm trying to say. Actually I'm not entirely sure either, so I can't explain it properly. It is fine as long as you can somewhat grasp where I'm going here.)

Let’s take it a step further and explore how the "structure of the world" and the "structure of language" are equivalent. The image below is of Van Gogh’s bedroom in Arles. The structure of the world is as follows:
![arles](/images/arles.jpg)
- First, at the smallest level, there are "objects" like the picture frame, the square, the wall, etc. In the structure of language, this corresponds to "names."
- Multiple objects combine to form "states of affairs." For example, "The picture frame is square," or "The wall is blue." In the structure of language, this corresponds to "elementary propositions."
- Multiple states of affairs combine to form "facts." For instance, "The square picture frame is hanging on the blue wall" is an example. In the structure of language, this corresponds to "complex propositions."
- Finally, facts combine to form the "world." The world aligns with language.

According to this theory, the "world" is the sum of statements like "The square picture frame is hanging on the blue wall," "The king-sized bed is placed in the right corner of the room," and so on. Writing this still leaves me a bit confused, but if you get a rough sense of what I mean, it should be enough to understand my point. If you still don’t get it, consider this example:

Just a moment ago, I said:

At the smallest level, there are "objects" like the picture frame, the square, the wall, etc. In the structure of language, this corresponds to "names."

There’s an interesting point here if you think about it. I used language to describe objects like "picture frame" and "square." There’s no other way to express them without language. Earlier, I said that "language is the tool for thinking." Look at this — we can’t even recognize objects without using language.

So, language is the tool for understanding the world, and furthermore, it’s why the structure of the world and the structure of language are identical.



## 3. The Meaning of the Picture Theory as Seen Through LLM Multi-Agent Systems

Philosophical discussions like these may seem abstract at first glance, but within the context of AI technology, they take on a much more practical significance.

Recently, I came across a very interesting paper: [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/pdf/2304.03442.pdf) by Stanford researchers, and the content is quite fascinating.
![simulacre](/images/simulacre.webp)

Here’s a rough summary: They created multiple NPCs (non-player characters) in a game world, each equipped with a large language model (LLM) like ChatGPT. When they let these NPCs freely roam around in the game environment, they began forming friendships with each other, some even started romantic relationships, and eventually, they held a mayoral election. This is just one example of many ongoing studies where LLM agents are given roles and allowed to communicate with each other (e.g., ChatDev, Autogen, etc.).

Of course, having LLMs talk to each other is fun, but what really caught my attention was the interaction with the surrounding environment (as described in section 3.2 of the paper). In this study, all events happening around the NPCs are described in natural language and communicated to them. For example, let’s say an NPC approaches a desk in the game world. The system would inform the NPC with a message like this: “The desk is not being used by anyone, and there are a laptop and some papers on top of it.” In the image below, you can see that all these trivial details are recorded for the NPC.
![memory stream](/images/memorystream.webp)


Isn't that amazing? These NPCs perceive the world through the medium of "language." According to the Picture Theory, this is no different from how humans perceive the world.

![gpteam](/images/gpteam.webp)
The meaning of this becomes even clearer in the GPTeam project. [Here’s a blog post](https://blog.langchain.dev/gpteam-a-multi-agent-simulation/) about GPTeam. Unlike the previous paper, there’s no visual game screen in GPTeam. Instead, the "world" is established in a language-based simulation. In this case, the world called "Jest Jockeys" consists of two locations: a shopping mall and a park. There are NPCs like Marty, Rebecca, and Ricardo. Once the simulation starts, you see a screen like the one below:
![jest jockeys](/images/jestjockeys.webp)
There are no visuals of NPCs walking around. Everything happening in the "Jest Jockeys" simulation world is expressed solely through language. And just by reading this, we can understand what’s going on. Once again, Wittgenstein’s words come to mind: “The structure of language and the structure of the world are the same.”

So what does all this imply? Understanding language means understanding the world, and when a machine understands language, it might mean, in a certain sense, that the machine understands the world. Stable Diffusion can create deepfake images, but that doesn’t make it human. AlphaGo can play Go exceptionally well, but that doesn’t make it human. However, if something like ChatGPT truly understands "language," could we say it might have the potential to become human?

Of course, to continue this discussion, we would need to delve into the debate about whether "language truly defines the limits of thought." Many people don’t agree with this idea. Even Wittgenstein himself later rejected the Picture Theory in his later philosophy and introduced the concept of context. But exploring that would be exhausting, so I’ll stop here for today. :)
