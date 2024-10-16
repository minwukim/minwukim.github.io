---
title: 'Abilities of LLMs and Information Density in Language'
permalink: /posts/information-density/
# tags:
#   - cool posts
#   - category1
#   - category2
---

## Idea of information density
This is a small snippet of [Nvidia fireside chat](https://www.youtube.com/watch?v=I6qQinoY9WM) with Ilya Sutskever & Jensen Huang (38:30~)

*Consider the concept of colors. It seems intuitive that one would need to see in order to truly understand colors. Yet, text-only neural networks—having never encountered a single photon—can still correctly identify which colors are more similar to each other. For example, they know that red is more similar to orange than to blue, or that blue is closer to purple than to yellow.*


*How does this happen? One possible explanation is that information about the world, including visual information, gradually seeps into text. It might take longer, but since there is so much text available, these models can still learn a great deal. Of course, when you incorporate vision into learning, you'll gain additional insights that aren't captured through text alone. However, I wouldn't say there are things that are entirely impossible to learn from text. Rather, it's more of a continuum—a kind of exchange rate. Particularly, if you're a human trying to learn from billions or even hundreds of billions of words, other sources of information, like visual input, naturally become more important.*

일리야 서츠케버는 exchange rate을 사용했지만, 나는 information density라는 표현이 더 나은 것 같다. 요지는 무엇이냐면, 학습된 데이터 속에 world knowledge에 대한 정보의 밀도는 아주 작으나, 그 학습데이터의 절대적인 양이 워낙 크다 보니, 그런 데이터로 학습이 된 LLM 역시 꽤 쓸만한 세계 지식의 습득 능력을 가질 수가 있는 것이다.

약 2년전 ChatGPT가 처음 나왔을 때, 저명한 언어학자 노엄촘스키가 뉴욕타임즈에 이에 대한 의견을 밝힌 [기고문](https://www.nytimes.com/2023/03/08/opinion/noam-chomsky-chatgpt-ai.html?unlocked_article_code=1.SU4.f3Eh.s2vEbRwBIBLR&smid=url-share)이 있다. 대충 요지는, 단순히 다음 단어/토큰을 예측하는 것만으로는 결코 인간의 지능을 모방할 수 없다는 것이었다. 수십년 전부터 변형생성문법과 언어 습득 장치(LAD, Language Acquisition Device)를 연구하고 설파하던 학자다운 주장이다. 하지만 현재 SOTA LLM을 보면 이런 주장은 상당 부분 틀렸다고 봐도 무방할 것 같다. 왜냐, LLM의 방대한 학습 정보에는 world knowledge, 그리고 사람의 사고방식에 대한 정보도 모두 낮은 밀도지만 분명하게 함유하고 있기 때문이다. 

아무튼, "언어의 정보 밀도"라는 개념을 가지고 LLM을 바라보면, LLM의 특성에 대해 보다 더 깊은 이해를 할 수가 있다. 

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

## 가설: reasoning 능력을 높이는 가장 근본적인 방법 - 양질의 데이터.

요즘 reasoning LLM관련 논문들을 보면, 많은 경우 따분한 피로감을 느끼는 경우가 많았다. 트리구조나 강화학습 등의 방법론에 너무 매몰이 되어, 방법론이 본질에 우선하는 주객전도의 경우를 많이 보았다. 하지만 훌륭한 연구는 본질에 충실해야 하며, 그렇지 못한 연구는 결코 문제 해결을 해낼 수 없을 것이라고 생각한다.

그렇다면 reasoning 능력의 본질은 무엇일까. 앞서 얘기했듯, 바로 학습데이터 속 추론과정 정보의 양이다. 현재 학습데이터는 그 양이 너무 미미해,


