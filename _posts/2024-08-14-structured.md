---
title: 'From Unstructured to Structured - A Quatitative Breakthrough of Data'
date: 2024-08-14
permalink: /posts/unstructured/

---

To some, Bitcoin is merely a piece of data, but to others, it's an intellectual phenomenon that encapsulates modern economic history, geopolitics, and human nature. A single technology can hold vastly different meanings depending on one’s perspective (I’m a Bitcoin maximalist btw). The more you know—and the more imagination and insight you possess—the deeper that meaning becomes.

The more I observe LLMs, the more this thought resonates. Some dismiss LLMs as limited because they simply predict the next token autoregressively. But I disagree. The potential of a machine that has mastered language is immense and will advance much further, depending on how much imagination we’re willing to apply.

## The Trade-off Between Structured and Unstructured Data

For my thesis, I spent about a year building a model to predict activist fund targets. The most challenging part was data preprocessing. For example, the less trusted a CEO is, the more susceptible the company is to activist funds. To reflect this, I used the CEO’s tenure as a metric. But tenure alone doesn’t perfectly indicate trust—long tenure doesn’t always mean trust, and short tenure doesn’t always imply a lack of it. The company’s context needs to be understood for proper judgment. Thus, simple tenure or turnover rates don’t fully capture this dynamic.

Other challenges included deciding how to normalize the data, whether to group comparisons by industry, whether to sort by market cap and split into 10 bins, how to handle outliers when the denominator is too small and the quotient becomes too large, and finding a balance between over-editing (introducing my own bias) and under-editing (leading to distortions). These questions consumed months of work.

At its core, data preprocessing is about compressing as much information as possible into numerical form. But why compress into numbers? There are two reasons: 
1. Numerical data must be structured to enable machine learning and statistical analysis.
2. Convenience. Compressed numerical data makes comparison and analysis easier, as seen with financial metrics like PER and ROE. In finance, such simple number-based comparisons are called relative valuation.

However, this compression inevitably leads to information loss, which can introduce noise and impair the accuracy of the analysis. The results often come with ambiguity and distortion.

This is why analysts in finance conduct qualitative research on specific companies (known as absolute valuation). But this method cannot scale—it’s time-consuming and difficult to automate because it relies on human contextual understanding. Thus, the industry adopts a labor-intensive approach by hiring many analysts, which is far from scalable.

Ultimately, the core issue is the trade-off between the ease of data processing and the freedom of its structure.

## A Breakthrough with LLMs

How can we overcome this trade-off? How do we ensure freedom in data structure while maintaining ease of processing? When I think about it, language is the highest-freedom data structure in finance. After all, 10-K filings and other financial disclosures are written in language.

Now, the question becomes: how do we ensure ease of processing for language data? Before ChatGPT in 2022, most research focused on encoder-based models like BERT. But encoding is also a form of data compression—it maps text into vectors in a multidimensional space. Unlike traditional financial multiples, these vectors are machine-learned numbers, meaning they lack standalone intuitive meaning for humans. Encoding only holds meaning in relative contexts. This is why encoder-based analysis achieves limited ease of processing, and ambiguity remains.

However, with the emergence of LLMs, the landscape has changed. The power of LLMs lies in their text-in, text-out approach. They map language data back into language, drastically improving the ease of processing. This improvement means that much intellectual labor can be automated and scaled up at a lower cost.

At this point, the conclusion seems to be heading toward the familiar idea that “LLMs will replace a significant portion of intellectual labor.” While that may be true, the perspective of viewing this through the lens of data freedom and ease of processing offers an important insight. For me, I’m still very interested in informatics or industrial engineering projects, and I can’t help but wonder how this text-to-text tool called LLM can solve problems that couldn’t be addressed before.
