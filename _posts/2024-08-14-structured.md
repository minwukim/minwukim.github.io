---
title: 'From Unstructured to Structured - A Quatitative Breakthrough of Data'
date: 2024-08-14
permalink: /posts/unstructured/

---


A single technology can hold vastly different meanings depending on one’s perspective. The more you know—and the more imagination and insight you possess—the deeper that meaning becomes. The more I observe LLMs, the more this thought resonates. Some dismiss LLMs as limited because they simply predict the next token autoregressively. But I disagree. The potential of a machine that has mastered language is immense and will advance much further, depending on how much imagination we’re willing to apply.

##  The Tradeoff between Scalability and the Richness of Information, and the value of LLMs.

It’s quite funny how my research interests have evolved over time. Right now, I’m fascinated by understanding the characteristics of LLMs and figuring out how to maximize their cognitive abilities. But honestly, I’m pretty new to this area—it hasn’t been long since I started diving into it. For most of my undergraduate years, I was deeply into computational social science, especially topics related to corporate finance and macroeconomics. Finance has always been a passion of mine, so naturally, my research revolved around it.

My thesis project was quite the journey. I spent about a year building a model to predict which companies activist hedge funds might target next. Looking back, it was challenging but rewarding to explore the dynamic mechanisms behind how these funds select their corporate targets using machine learning. (A side note: activist investing is that strategy where funds buy significant shares of a company and get actively involved in management to improve profitability. The idea is to pump the stock price for profit, and their announcements usually spark short-term price spikes.)

Looking back, this experience taught me something crucial about computational social science. There’s this **tradeoff between scalability and the richness of information**. On one hand, statistical models and machine learning make it easy to process large datasets, enabling broad comparative analyses. But on the other hand, these approaches inherently compress information into numerical form, which inevitably means losing some of it. 

Take my activist fund research, for example. I used CEO tenure as a proxy for how much support a CEO has within their company. Sure, it’s measurable, but it’s such a simplification. A long-serving CEO might actually be a lame duck, while a newly appointed CEO could have an impeccable reputation from years of internal service. A single number just can’t capture those nuances. To dig deeper, qualitative research—where someone reads reports, news articles, and other sources to piece together the bigger picture—would have been ideal. But that kind of work is labor-intensive and isn’t scalable. It’s exhausting and slow because it depends so much on human effort.

How can I overcome this tradeoff? This question is probably what nudged me toward LLMs. For breakthrough, we need a system capable of rapidly processing large amounts of data with minimal compression, and LLMs are precisely that system. **Language is the most expressive form of information for conveying human thought**, offering far more flexibility and information density than numerical data. Therefore, a machine that comprehends and generates language enable us to deal with these vast and complicated information in an unprecedentedly large scale.


## Layers of Challenges and the Leap Through LLMs

I’ve been thinking a lot lately about the different levels of problems in artificial intelligence and how LLMs might serve as a bridge to the next stage. 

Here’s how I (very crudely) classify these levels:  
1. Tasks related to text, images, and sound.  
2. Problems requiring human intuition and reasoning, like those in economics or politics.  
3. Issues tied to humans and cognitive science.  

Let’s leave the third level for another time and focus on the first one for now.

AI is progressing rapidly through the first stage. LLMs can talk like humans, tools like Sora can create incredible videos, and though I’m not as familiar with audio, AI singers are already covering songs at an impressive level. On top of that, multimodality—the ability to work across text, image, and sound—is advancing quickly. Why is this even possible? At its core, it boils down to the sheer abundance of data. According to the universal approximation theorem, neural networks approximate functions based on a dataset, so having an immense amount of data is key to strong learning. And when it comes to text, images, and sounds, the internet is overflowing with data. That’s why AI can excel here.

But has the second stage—problems requiring intuition and reasoning—been conquered? I’m not so sure. Take finance, a field I know reasonably well. Sure, math wizards in quant finance at firms like Citadel or Renaissance Technologies are raking in money, but traditional investing giants like Warren Buffett, Seth Klarman, and Howard Marks remain relevant. That suggests they possess abilities that computers haven’t mastered yet.

So what exactly are those abilities? It’s hard to define, but I’d say it’s something like insight, intuition, or the ability to "connect the dots." For example, consider this question:  
*"In March 2020, Jerome Powell unleashed quantitative easing to combat COVID-19’s economic impact. What might happen to the financial markets?"*  

Machines struggle here, mainly because there’s so little data to reference. In this world, a pandemic like COVID-19 has happened only once. There’s no dataset to draw from. Even in traditional finance data, metrics like GDP (measured quarterly) or FOMC meetings (held every 45 days) offer limited points. To gather more data, we’d need to simulate the universe hundreds of times—but unfortunately, we’re not Doctor Strange.

*(Side note: In quant finance, there are two common approaches to address this limitation. First, shrink the time horizon to generate more data—monthly trading provides 12 data points per year, daily provides ~300, and going down to milliseconds or nanoseconds yields even more. That’s why HFT and market-making strategies are so profitable. Second, use causal inference models to mathematically explain phenomena. Personally, I’m skeptical of this approach; it relies too heavily on assumptions and leaps of logic. Even Daron Acemoglu’s Nobel-winning work on colonialism and economic prosperity has notable flaws upon closer inspection.)*

Humans, on the other hand, excel at finding patterns in sparse data. Take Powell’s quantitative easing as an example. A person might connect it to historical instances like Bernanke’s QE during the 2008 financial crisis or Japan’s Abenomics in 2012 to identify patterns. People call this insight or intuition; social scientists call it case study; AI researchers call it transfer learning.

But **LLMs** change the game. Here’s why—both from a data perspective and a logical perspective.

### The Data Perspective  
The fact that machines can now "use language" significantly expands the amount of usable data. Previously, models could only analyze discrete numbers like GDP, interest rates, or stock prices. Language, however, is far richer in context and nuance. By incorporating language, we can essentially create more "data" without needing parallel universes to generate it. 

### The Logical Perspective  
LLMs can "understand language" and encode "logic" through it. Imagine Buffett or Howard Marks writing an essay comparing Bernanke in 2008 and Powell in 2020 to predict future outcomes. They would lay out their reasoning in detail. If enough high-quality analyses like this were fed into an LLM, it could potentially become an exceptional investor. Of course, gathering such premium data is no small feat—especially in finance, where strategies are closely guarded. But this approach seems far more promising than simply plugging numbers into a model.

Ultimately, the fact that machines now understand language represents a groundbreaking innovation.


## Benchmarking Problems and Measuring Intelligence

Here’s where my thoughts start to get a bit scattered.

One of the ongoing challenges in AI research is benchmarking. Problems like math questions or multi-hop reasoning don’t fully capture the capabilities of LLMs. Developing better benchmarks is an active area of exploration.

I’ve been mulling over this too, and it seems that to truly measure higher-level intelligence, we need to move away from easily verifiable problems. 

This ties into how I think about "intelligence." Take, for example, an Olympiad medalist who excels at solving complex problems and someone like Warren Buffett, who demonstrates exceptional insight in investing. Both are highly intelligent, but isn’t the latter type of intelligence—the kind that shapes industries and leaves a lasting legacy—more impactful? After all, history remembers visionaries like Elon Musk, not people who were great at solving math problems.

The problem, though, is that this kind of intuition and insight is difficult to quantify. So how do we measure it? Here’s an idea I had:  
We could train an LLM on data up to a certain point—say, 2023—and then ask it to predict events in 2024. These could be political developments, investment returns, or metrics like Sharpe ratios. By doing so, we might be able to heuristically measure the LLM’s reasoning and high-dimensional thinking.

Anyway, this is just an early thought, and it’s still rough around the edges. But I’ll stop here before I go further off track.

