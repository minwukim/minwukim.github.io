---
title: 'Abilities of LLMs and Information Density in Language'
permalink: /posts/information-density/
# tags:
#   - cool posts
#   - category1
#   - category2
---

## Idea of Information Density
This snippet is from an [Nvidia fireside chat](https://www.youtube.com/watch?v=I6qQinoY9WM) with Ilya Sutskever and Jensen Huang (38:30~).

*Consider the concept of colors. It seems intuitive that one would need to see in order to truly understand colors. Yet, text-only neural networks—having never encountered a single photon—can still correctly identify which colors are more similar to each other. For example, they know that red is closer to orange than to blue, or that blue is closer to purple than to yellow.*

*How does this happen? One possible explanation is that information about the world, including visual information, gradually seeps into text. It may take longer, but since such a large amount of text is available, these models can still learn a great deal. Of course, when you incorporate vision into learning, you'll gain insights that aren't captured through text alone. However, I wouldn't say there are things entirely impossible to learn from text. Rather, it's more of a continuum—a kind of exchange rate. For humans learning from billions or even hundreds of billions of words, other sources of information, like visual input, naturally become more important.*

Sutskever used the term "exchange rate," but I think "information density" is a better fit. The point is, although the density of world knowledge in the training data is low, the sheer volume of that data enables LLMs to acquire useful world knowledge.

About two years ago, when ChatGPT first emerged, the renowned linguist Noam Chomsky shared his thoughts in an [op-ed](https://www.nytimes.com/2023/03/08/opinion/noam-chomsky-chatgpt-ai.html?unlocked_article_code=1.SU4.f3Eh.s2vEbRwBIBLR&smid=url-share) for The New York Times. His main argument was that simply predicting the next word or token could never replicate human intelligence—an opinion reflecting his decades of work on transformational grammar and the Language Acquisition Device (LAD). However, looking at the current state-of-the-art LLMs, it seems clear that his assertion is, at least partially, incorrect. This is because the vast amount of training data LLMs consume contains not only world knowledge but also insights into human cognition—albeit at a low density.

Ultimately, viewing LLMs through the lens of "information density" offers a deeper understanding of their capabilities. 

## Three Abilities of LLMs
LLMs (Large Language Models) possess three different abilities. The first is the ability to use language (including grammar, vocabulary, etc.). The second is the ability to understand world knowledge. The third is reasoning ability. If we were to rank these abilities relatively, the ability to use language is the strongest, world knowledge comes second, and the weakest is reasoning.

To understand why this phenomenon occurs, we need to recognize two points:

1. The abilities of LLMs stem from their training data (I will not discuss factors like model structure or model parameters here).
2. Language serves as a medium that contains information, and the density of information varies with each type.

Then let’s explore the three types of information:

**First is linguistic information.** Linguistic information has the highest density since every sentence people use contains information about grammatical structure and vocabulary. This is why LLMs excel at language proficiency. Mistakes in word choice or grammar are now almost nonexistent for LLMs

**Second is world knowledge.** Language inherently contains much information about the world, but its density is not comparable to linguistic information. While linguistic information is inherently embedded in natural language, world knowledge can only be found in language that contains meanings about specific fields. This is the source of the hallucination problem in LLMs. Without the right world knowledge, an LLM cannot provide accurate answers. For example, people criticize LLMs for being "stupid" when they cannot answer questions about common sense (like physical laws). This, fundamentally, is an issue with the data. People do not usually put obvious common-sense knowledge into words, so the information density of such common sense in the training data is inevitably low.

**Third is reasoning ability.** The density of information in reasoning processes is even lower. Reasoning itself is a high-level cognitive process, even for humans, so its information content in language is scarce. Even if the reasoning process is articulated in words, much of it is likely to be omitted. For instance, mathematical papers contain a relatively high density of reasoning information, but they often omit much of the trial and error that mathematicians go through, presenting only the refined final conclusions. Therefore, LLMs trained on linguistic data with low reasoning information density are naturally weak in reasoning ability.

Next, we need to review the efforts made to improve these three abilities.

**First is language proficiency.** There isn’t much room for improvement here. LLMs’ language proficiency is already excellent. It has been sufficiently proven that, with enough training data and parameters, language proficiency can be guaranteed.

**Second is world knowledge.** There are two main methods for this. The first is to input more training data (fine-tuning), and the second is to make the model reference external data (RAG). Going a bit further, there are attempts like GraphRAG, which allows LLMs to understand the full context of external data like humans do, and MemGPT, which controls short-term and long-term memory like a computer's operating system. However, these topics will not be covered in this article.

**Third is reasoning ability.** The most effective method for enhancing reasoning ability has been Chain of Thought (CoT), refers to a simple prompt engineering that asks the LLM to provide an answer step-by-step rather than giving a direct response. CoT has proven to be significantly effective. Subsequent methods like SC-CoT, ToT, PRM, ORM, and MCTS can all be seen as variations or extensions of CoT. The core of all these methodologies is breaking down complex problems into smaller, manageable parts. Also, I observed one of the recent trends in the academia is the multi-turn instrinsic self-correction (like RISE or SCoRE paper), but I won't go into those details in this article.

Of course, this is just a classification for easy understanding; these three abilities cannot be perfectly separated like slicing something with a knife. In most cases, the three abilities improve synergistically.


## Hypothesis: The Fundamental Key to Improving Reasoning Ability—High-Quality Data

Recently, as I’ve been reading papers on reasoning in LLMs, I often find myself fatigued by the overly complex methods being proposed. Many seem to be fixated on methods like tree structures and reinforcement learning, placing the methodology before the essence of the problem. I believe that truly impactful research must remain grounded in the core of the issue; otherwise, it will fail to solve the problem.

So, what is the essence of reasoning ability? As mentioned earlier, it's the amount of information about the reasoning process embedded in the training data. However, the current issue is that this information is far too sparse. The total amount of reasoning information is a product of the information density and the volume of language data. No matter how much data we have, if the density of reasoning information is too low, the overall amount of that information remains limited.

The solution, then, seems simple: Why not capture all the reasoning processes happening in the human mind into linguistic form and train models on that data? This is the hypothesis I’m considering.

However, two bottlenecks emerge here:
- **First**, how do we obtain such data?
    - This problem seems to require more understanding of fields like linguistics, psychology, logic, and psychoanalysis, rather than pure computer science.
- **Second**, how much of this data is necessary?
    - Meta AI explored a similar philosophy (quality over quantity) in a paper called [LIMA](https://arxiv.org/pdf/2305.11206), where they used at least 1,000 examples. In my case, since the text would also need to contain logical information, it would likely be much longer, requiring even more data to capture the relevant patterns.

Going any further would lead to specific research ideas, so I’ll leave it here for now.

