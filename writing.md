---
layout: default
title: Writing
---

# Writing

My 5 most recent posts. For the full archive, browse by tag below.

{% assign recent_posts = site.data.posts | sort: "created" | reverse | slice: 0, 5 %}
{% include post_list.html posts=recent_posts %}

## Browse by tag

{% assign all_tags = site.data.posts | map: "tags" | join: "," | split: "," | uniq | sort %}
{% for t in all_tags %}[#{{ t }}](/tags/{{ t }}.html){% unless forloop.last %} · {% endunless %}{% endfor %}

## Elsewhere

These live on other platforms (not yet mirrored to this site).

### Life reflection
- [Mindset](https://dynalist.io/d/IfWvgrSkDIZuFvikXF9Z_1_V)
- [Computational kindness (talk)](https://www.youtube.com/watch?v=0OCmHuxWkks)
- [On being value-oriented](https://medium.com/@sjonany/on-being-value-oriented-42342c5f9463)
- [Focus on the undervalued](https://medium.com/@sjonany/monthly-learning-may-2025-focusing-on-the-undervalued-llm-correctness-music-production-e37028eaed37)

### Book notes
- More on [medium](https://medium.com/@sjonany)

### Computing — LLM
- [Practical hallucination mitigation strategies](https://medium.com/@sjonany/practical-hallucination-mitigation-strategies-771ed64b8285)
- [Transformers for software engineers (in Python)](https://medium.com/@sjonany/transformers-for-software-engineers-in-python-1d5b287aadc5)
- [Transformers QK, OV, induction circuit](https://medium.com/@sjonany/transformers-qk-ov-induction-head-ddd3e4d9d73e)
- [Transformers doing math](https://medium.com/@sjonany/transformers-doing-math-e544b8486ff2)
- [Mechanistic Interpretability — first look](https://medium.com/@sjonany/mechanistic-interpretability-first-look-bc62d2120c2f)
- [Building Reliable LLM-based apps: The “Good Enough” Trap](https://medium.com/@sjonany/building-reliable-llm-based-apps-the-good-enough-trap-f2c23a952219)
- [AI-executable natural-language contracts](https://blog.blockmagnates.com/ai-executable-natural-language-contracts-1669373b1428)
- [Can AI be funny? An exploration with texting on Android and ChatGPT](https://medium.com/@sjonany/can-ai-be-funny-an-exploration-with-texting-on-android-and-chatgpt-911af17f9b00)

### Computing — Privacy
- [Chrome extensions can steal your data — what you can do to mitigate this](https://medium.com/@sjonany/chrome-extensions-can-steal-your-data-what-you-can-do-to-mitigate-this-9c66c81993ec)
- [Budget composition in differential privacy](https://medium.com/@sjonany/budget-composition-in-differential-privacy-5fb793465bc6)
- [Usable differential privacy: A tool to navigate the privacy-utility tradeoff](https://medium.com/@sjonany/usable-differential-privacy-a-tool-to-navigate-the-privacy-utility-tradeoff-51d3ae9559a5)
- [Correcting (ϵ, δ) misconception in differential privacy](https://medium.com/@sjonany/correcting-%CF%B5-%CE%B4-misconception-in-differential-privacy-e830dbdce0ab)
- [GDPR, de-identification and compliance examples](https://medium.com/@sjonany/gdpr-de-identification-and-compliance-examples-86dbf5efc855)
- [De-identification / anonymization terminology, and why it’s confusing](https://medium.com/@sjonany/de-identification-terminology-and-why-its-confusing-e753846e7917)

### Computing — Statistics
- [Comparing two binomial random variables](https://medium.com/@sjonany/statistics-comparing-two-binomial-random-variables-f504a71343a1)
- [P-values when comparing two binomial random variables](https://medium.com/@sjonany/p-values-when-comparing-two-binomial-random-variables-6c091fbe7f11)

### Hobbies
- [How to convert lead sheet PDF to irealpro](https://medium.com/@sjonany/how-to-convert-lead-sheet-pdf-to-irealpro-65fd0725aaea)
- [Badminton forehand smash](https://medium.com/@sjonany/badminton-forehand-smash-755a13a37193)
