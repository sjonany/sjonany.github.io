# Unregulated AI Use Harms Learning
*Published 2026-07-08*

*Tags: [#education](/tags/education.html)*

This post poses a **problem statement**: that a CS course that does not regulate AI usage risks setting up students for failure.

Here's the abstract:
**Unregulated** use of AI in courses breaks the out-of-classroom learning process, which is the majority of the learning time. It does so by providing a convenient, less guilt-inducing way to shortcut the hard thinking on **homework**. In bypassing [important, strenuous active mental processes](https://sjonany.github.io/posts/how-to-build-mental-models-for-cs-concepts.html), students then fail to develop robust mental models.

## Evidence that this is a real problem
**Berkeley highest failure rate.** As of June 2026, UC Berkeley computer science classes had a [much higher failure rate](https://www.dailycal.org/news/campus/academics/failing-grades-soar-as-professors-see-greater-ai-usage-dwindling-math-skills-in-uc-berkeley/article_16fad0bf-02cb-4b8c-8d88-888ffd9f8608.html) than in the past. Some instructors attribute it to AI usage.
> Garcia believes the “primary driver” of these abnormally high failing rates is due to a “vast increase in academic dishonesty” due to students’ usage of large language models, such as Claude, ChatGPT and Google Gemini.

**Instructor surveys.** In [Prather et al. (2025)](https://doi.org/10.1145/3689187.3709614), instructors reported a higher level of academic dishonesty and poorer performance on proctored exams. Here is an illustrative quote:
>I don’t think we’ve ever had such large numbers of students who go into a test and simply can’t do anything.

## Root causing: Cognitive offloading for homework
This is speculative, but I suspect that the main way in which AI harms learning is because students no longer learn well **outside of the classroom** -- because the cognitive effort for doing **homework is offloaded to AI**.

**Why I focus on homework** is because the course curriculum and in-person exams have not changed that much recently. One big change, instead, is how students **learn outside** of the classroom, and most of the learning happens through their **homework**. In support of this hypothesis, the previous section mentioned some instructors attributing the reduction in learning to academic dishonesty -- this most likely happens in unproctored settings, like when students are doing their homework.

**Cognitive offloading.** How does using AI on homework hinder learning? One possible reason is due to cognitive offloading ([Risko & Gilbert, 2016](https://doi.org/10.1016/j.tics.2016.07.002)), but there are more -- [Bernstein et al., 2025](https://doi.org/10.1145/3769994.3770036) has a more comprehensive, AI-specific list if you want more ammo. Your brain needs to go through several [active processes](https://sjonany.github.io/posts/how-to-build-mental-models-for-cs-concepts.html) to capture new mental models. If you offload the cognitive work to another intelligence (an AI, or another human), the mental model never forms in your brain.

## How this is worse than pre-AI
Even though pre-AI, cognitive offloading on homework was already a problem, this problem is exacerbated by AI for these reasons:

**Accessibility.** You no longer have to pay the social cost of asking your classmate for the answer. You can bypass the hard thinking with just a few seconds of typing. So, the **cost** of cheating is lower than it used to be.

**Illusion of competence.** You spend a minimal effort writing down your question, and instead of attributing the answer ownership to a non-human AI, you might intuitively feel that it is **you** who own the answer. After all, in the chatbox is just you and ... well, the AI. It is easy to feel that the personalized AI chat is an extension of you, more so than you feel like a publicly available solution manual or a classmate is an extension of your thinking. Finally, this mistaken ownership misleads you into thinking that it was your competence that produced the work. [Bernstein et al. (2025)](https://doi.org/10.1145/3769994.3770036) mentioned the term "illusion of competence" to capture this effect. The result, then, is that you **feel** like you crushed the homework, only to be surprised by how you are unable to repeat the same performance during in-person exams.

## Next steps
If turning a blind eye to AI usage is setting up students for failure, then what can educators do? Can we do better than just writing an AI policy doc? Can we do more so that we can use AI to **accelerate** learning instead - and what's actually practical for a single instructor? We'll tackle this on a future post...

## References
- Risko, E. F., & Gilbert, S. J. (2016). Cognitive offloading. *Trends in Cognitive Sciences, 20*(9), 676–688. https://doi.org/10.1016/j.tics.2016.07.002
- Prather, J., Leinonen, J., Kiesler, N., Gorson Benario, J., Lau, S., MacNeil, S., Norouzi, N., Opel, S., Pettit, V., Porter, L., Reeves, B. N., Savelka, J., Smith, D. H., Strickroth, S., & Zingaro, D. (2025). Beyond the Hype: A Comprehensive Review of Current Trends in Generative AI Research, Teaching Practices, and Tools. In *2024 Working Group Reports on Innovation and Technology in Computer Science Education (ITiCSE-WGR '24).* ACM. https://doi.org/10.1145/3689187.3709614 (arXiv:2412.14732)
- Bernstein, S., Rahman, A., Sharifi, N., Terbish, A., & MacNeil, S. (2025). Beyond the Benefits: A Systematic Review of the Harms and Consequences of Generative AI in Computing Education. In *Proceedings of the 25th Koli Calling International Conference on Computing Education Research (Koli Calling '25).* ACM. https://doi.org/10.1145/3769994.3770036 (arXiv:2510.04443)
- The Daily Californian (June 2026). *Failing grades soar as professors see greater AI usage, dwindling math skills in UC Berkeley.* https://www.dailycal.org/news/campus/academics/failing-grades-soar-as-professors-see-greater-ai-usage-dwindling-math-skills-in-uc-berkeley/article_16fad0bf-02cb-4b8c-8d88-888ffd9f8608.html
- Jonany, S. (2026). How to build mental models for CS concepts. https://sjonany.github.io/posts/how-to-build-mental-models-for-cs-concepts.html

*Comment via: [medium](https://medium.com/p/1564182ad146), [substack](https://stephenjonany.substack.com/p/unregulated-ai-use-harms-learning), [linkedin](https://www.linkedin.com/pulse/unregulated-ai-use-harms-learning-stephen-jonany-cupmc/)*
