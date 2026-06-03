# Why AI Won't Kill CS 101
*Published 2026-03-12*

*Tags: [#education](/tags/education.html)*

Q: Should we still teach CS freshmen how to code in Python even when we reach a stage where AI can do the coding for them?

A: Yes, because coding is an effective learning mechanism to learn about computing concepts, and we need this literacy to navigate some nuanced trade-offs of complex real-world systems.

— Now let us dive deeper.

[Previously](why-you-still-need-to-learn-even-when-ai-can-do-anything.md), I argued that even when AI can do everything for you, humans still have to learn and be able to compute some complex concepts in real time, in order to collaboratively want better. But what are these complex concepts? For this post, let’s focus on a specific aspect of computer science education.

## You need to read and write code to learn computing concepts — because coding is active learning

Let’s take a look at what you learn as a CS freshman. Using a language like Python, you would learn how to read, think through, make mistakes, and debug concepts like conditionals, loops, and function compositions. I remember my very first encounter with loops and functions — I had to play around in my IDE and make mistakes before I finally “got it.” This act of playing around requires something that is easy to read, edit, and run — and a programming language like Python is a good example. You could also say that coding is a very active form of learning, and this interactivity helps you understand concepts better. These basic concepts are then prerequisites for learning about data structures and algorithms, which IMO are really powerful mental toolkits for anyone to have. And this brings me to my next point…

## Computing concepts are needed to “want” better

You need the concepts taught in data structures and algorithms classes to make design choices in some real-world systems. Let’s take a look at a few examples: resource prioritization and matching. When designing complex systems that have to satisfy conflicting interests of multiple human users, you might have to make decisions like “I prefer round robin instead of a priority queue based on a weighted average of the user’s features x,y,z because simplicity implies understandability and trust”, or “I want my dating platform to use the [Gale-Shapley](https://blogs.cornell.edu/info2040/2021/09/30/hinge-and-its-implementation-of-the-gale-shapley-algorithm/) algorithm and I know about its pros and cons.” The book [Algorithms To Live By](https://www.goodreads.com/book/show/29632790-algorithms-to-live-by) has more examples.

## Conclusion

I feel more optimistic about claiming that for the foreseeable future, it is useful for some people to take CS 101, where you would learn how to read, modify, and make mistakes with a programming language that teaches you loops, conditionals, and function composition. They set up the basis for you to learn complex computing concepts that are necessary to navigate real-world tradeoffs.

## Appendix: Weaker arguments

These are arguments that I initially considered, but later discarded.

Because AI might be malicious / have poor implementations. The argument here is that even if the AI understands your intention, it could implement something else that could be dangerous, and so it’s up to the humans who have code literacy to save the day. See [Anthropic’s blog post](https://www.anthropic.com/research/agentic-misalignment) for a clear example. However, as argued by the book [If Anyone Builds It, Everyone Dies](https://www.amazon.com/Anyone-Builds-Everyone-Dies-Superhuman/dp/0316595640), if the AI is more intelligent than a human, then they will be able to craft hidden implementations that humans would be hard-pressed to detect by just reading the code.

- In the more immediate future, where AI still makes human-correctable mistakes, this argument holds. Clawdbot is a good example — It is useful for most to understand common security concepts, and guide the AI to provide a safer implementation.

Because there are some use cases where you have to go down to the level of precision of code to achieve what you want. This I am less sure of. For most design decisions, I probably don’t need to go down to the level of for loops to dictate my preferences. I suspect for most design decisions I make, I could have just used a lot of vocab from my data structure and algorithms class without even mentioning the word “for loop”.

*Comment via: [medium](https://medium.com/@sjonany/humans-will-still-need-to-learn-how-to-code-even-with-ai-698b883658af), [substack](https://stephenjonany.substack.com/p/why-ai-wont-kill-cs-101), [linkedin](https://www.linkedin.com/feed/update/urn:li:activity:7437678161921830912/)*
