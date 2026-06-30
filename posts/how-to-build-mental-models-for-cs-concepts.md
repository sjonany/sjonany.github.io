# How to build mental models for CS concepts
*Published 2026-06-30*

*Tags: [#education](/tags/education.html)*

We previously argued for the importance of developing [mental models](https://sjonany.github.io/posts/mental-models-in-your-brain-or-the-ais.html). But, **how** does one develop them for computer science concepts like greedy algorithms?

## Mental model definition
We first refine our understanding of "mental models" with this quote from [Robins et al. (2019)](https://www.google.com/books/edition/The_Cambridge_Handbook_of_Computing_Educ/vmAwEAAAQBAJ?hl=en&gbpv=1&dq=+Robins,+A.+V.,+Margulieux,+L.+E.,+%26+Morrison,+B.+B.+(2019).+Cognitive+sciences+for+computing+education&pg=PA231&printsec=frontcover)
"Expert programmers are characterized by a large library of useful **schemata/plans** that chunk and organize significant amounts of information in a form that **reduces cognitive load**. Many of the difficulties experienced by novice programmers arise from their **lack of such organizing knowledge structures**." 

So! Mental models are like brain-shelves that allow you to think more efficiently. You would be able to load more concepts into working memory and manipulate them with less mental tax. The more you have, the more efficient your thinking is. Let's take a look at the mental processes needed to develop them. 

## Processes that develop mental models
As for how to develop these brain-shelves, you need to **actively** go through thinking tasks of **varying levels of guidance** in **varying contexts**.

### Mode: active
In all the phases that we will see in the later sections, the most important qualifier is that you must **actively** engage with the material. By active, we mean one where you **reconstruct from memory, without referring to external material.** This is one of the two techniques rated as "high utility" in [Dunlosky et al. (2013)](https://wcer.wisc.edu/docs/resources/cesa2017/Dunlosky_SciAmMind.pdf)'s review of learning strategies. Some examples -- Active: self-testing verbally while closing your eyes. Non-active: highlighting textbooks.

The "no external material" part makes sense (that means no looking at textbooks or AI output, mind you). The mental model exists in your head. To build this mental model, you need to **exercise** / shape / mold it enough such that you can reproduce the study material **without external help.** That's how you ensure that the mental model, on its own, is robust enough.

**In practice.** When I was a student, I tried to **reconstruct the lecture materials** from scratch on an empty piece of paper, and only looked at the lecture slide when stuck. This is like "self-quizzing", but more thorough in that I really do try to re-derive all the concepts, as opposed to just filling in small blanks. There's the pro that I don't have to create flashcards too! The flash card is the lecture slide itself.

More readings on active recall here if interested: [1](https://docs.google.com/document/d/1Q--oz2XvZJtX6Qdx2HrQYbIlbCmwhVbAWXD2-srTH7s/edit?tab=t.0) [2](https://docs.google.com/document/d/11-iWheKkmcLWZ7p1p8xUjxUin4X4TgvmGXv5l9OEITo/edit?tab=t.0#heading=h.p3r2l36od66)

### Phases
Okay, we emphasized that we must be **active** in how we approach our learning. Now we'll go through roughly-ordered phases that help you develop your mental model:
1. **Build** your initial model by going through and reconstructing the guided instruction / lecture slides
2. **Test.** Stress-test your mental model by doing practice problems from homework and quizzes
3. **Retain.** Review the material at a later date to make it stick.

**Build: Go through guided instruction.** You start by **reading** through **known** materials and **self-explain** these in multiple passes until you can go through all below **from scratch**. Here is a list of concepts that ideally exist in the guided instruction (i.e. your lecture notes). If you want the more authoritative source rather than my personal re-ordering, please see the references section below.
- **Example.** Go through a worked example. E.g. [video](https://youtu.be/2Vxl2HMpt2M?si=-tWhF0ACPbDJZmij&t=111). For a given concrete problem, work through example inputs and outputs, and a simulation run of the algorithm.
- **Direct schema explanation.** E.g. [video](https://youtu.be/lfQvPHGtu6Q?si=jVVRco5JB9LOm-_a&t=244). Explain the abstract concepts that are generalizable across the examples, like optimal substructure, then relate this to the examples.
- **Decomposition.** If the process has multiple logical subcomponents, label the subcomponents explicitly. E.g. [handout](https://web.stanford.edu/class/archive/cs/cs161/cs161.1138/handouts/120%20Guide%20to%20Greedy%20Algorithms.pdf). Especially for anything that's sequential like "First, define your solution, second define your measure, third prove that greedy stays ahead", give a **functional label** to each step and provide per-step examples.
- **Map to known mental models.** Map to familiar concepts so you can link to existing mental models. **Analogies** can work well here. E.g. To minimize total debt payment, you prioritize paying off the highest-interest debt first. You intuit that focusing on just the one highest-interest debt at a time will be best for you long term.
- **Negative examples.** Show common misconceptions. E.g. show intuitive approaches that are wrong and counterexamples.
- **Multiple examples.** Go through multiple examples to ensure that your mental model is of the right level of abstraction to at least generalize to them. E.g. [handout](https://usaco.guide/silver/greedy-sorting?lang=cpp)
- **Intuitive explanation.** You should **create** explanations that are intuitive to you by (1) Drawing a **diagram** and/or (2) Having a **one-liner explanation** that may sacrifice accuracy for intuitiveness. This personalized representation is the main form that you would invoke **in real life, outside of class**, and should be **personalized** to you. I usually do this at the end of every lecture by writing a **TL;DR** section at the top of the document with one-liner explanations of the important concepts. E.g. When I think of greedy algorithms I think of "pick locally optimal moves that are also proven to be globally optimal". Or when I think of "breadth-first search" I can visualize a cloud that expands concentrically from a middle point.

**Test: Practice / apply.** This is where homework comes in. You see if the mental model developed by going through the known materials is flexible enough to generalize to new materials.
- **Solve novel problems.** Go through [past exams](https://courses.cs.washington.edu/courses/cse421/25wi/files/exams/practice-midterm-1-solutions.pdf) or [programming contests](https://usaco.guide/silver/greedy-sorting?lang=cpp). 
- **Interleave problem types.** Go through a set containing problems of different types **without** knowing which technique to use to see if you know when to apply a certain technique vs another.

**Retain: Spaced repetition.** This is the only other top-rated tip from [Dunlosky et al. (2013)](https://wcer.wisc.edu/docs/resources/cesa2017/Dunlosky_SciAmMind.pdf). If you want something to stick, **review** it periodically. The scattered cadence of quizzes, homework, and exams kind of already does this for you. To quote: "To remember something for one week, learning episodes should be 12 to 24 hours apart; to remember something for five years, they should be spaced six to 12 months apart. Although it may not seem like it, you actually do retain information even during these long intervals, and you quickly relearn what you have forgotten."

## Putting things into practice
**Student.** As a student, after every lecture, do the following:
- **First pass.** Go through the lecture slides to see if you can understand each slide even on a passive read. If you don't understand something, ask someone / AI.
- **Augment.** Augment each slide with list items from the previous section that are missing. E.g. Use AI to come up with another example of the same concept, if you don't get it yet. Or you can also ask AI to decompose a complex algorithm into subcomponents and give each an intuitive one-word label.
- **Second pass: reconstruct.** Go to a room with 0 internet, an empty piece of paper, and a printout of the lecture slides. Regenerate the lecture slide by just looking at the slide title, but don't look at the slide detail unless you are stuck.
- **Third pass: intuition.** Put a TL;DR section at the top of your note. Give one-liner explanations and visuals of the important concepts.
- **Practice.** Do a lot of problems. Usually homework and past exams are enough. You should do the thinking on your own first, and only check the solution, or use AI after you're stuck for, say, more than 15 minutes. 

**Instructor.** As an instructor, the job is to create a learning environment that encourages students to go through all the mental processes as mentioned previously, both inside and outside of the classroom. This will be tackled in a future blog post. 

## What's next?
In summary, to develop mental models, you need to be able to **actively** reconstruct the material from memory and test it against a **variety** of problems. To retain them, you would revisit the material **at least a week** after you learnt it.

That's a lot of work though! In subsequent posts, let's see how **external agents** like CS educators and AI can help or hinder students as they go through these requisite mental processes.

## References
[Dunlosky, J., Rawson, K. A., Marsh, E. J., Nathan, M. J., & Willingham, D. T. (2013). What works, what doesn't. Scientific American Mind, 24(4), 46–53.](https://wcer.wisc.edu/docs/resources/cesa2017/Dunlosky_SciAmMind.pdf)
- Their full peer-reviewed review: [Dunlosky, J., Rawson, K. A., Marsh, E. J., Nathan, M. J., & Willingham, D. T. (2013). Improving students' learning with effective learning techniques. *Psychological Science in the Public Interest, 14*(1), 4–58.](https://pubmed.ncbi.nlm.nih.gov/26173288/)

Robins, A. V., Margulieux, L. E., & Morrison, B. B. (2019). Cognitive sciences for computing education. In S. A. Fincher & A. V. Robins (Eds.), *The Cambridge Handbook of Computing Education Research* (pp. 231–275). Cambridge University Press. https://doi.org/10.1017/9781108654555.010
- [Chapter 9.6](https://www.google.com/books/edition/The_Cambridge_Handbook_of_Computing_Educ/vmAwEAAAQBAJ?hl=en&gbpv=1&dq=+Robins,+A.+V.,+Margulieux,+L.+E.,+%26+Morrison,+B.+B.+(2019).+Cognitive+sciences+for+computing+education&pg=PA231&printsec=frontcover) is my main reference for the "guided instruction" section.

https://teachtogether.tech/en/
- The [six strategies](https://teachtogether.tech/en/#s:individual-strategies) section here has a lot of overlap, and a lot more references

*Comment via: [medium](https://medium.com/p/9c0a41571ae6), [substack](https://stephenjonany.substack.com/p/how-to-build-mental-models-for-cs), [linkedin](https://www.linkedin.com/pulse/how-build-mental-models-cs-concepts-stephen-jonany-obcfc/)*
