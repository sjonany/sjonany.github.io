# AI-proofing a CS Course
*Published 2026-07-11*

*Tags: [#education](/tags/education.html)*

Unregulated AI usage risks [setting up students for failure](https://sjonany.github.io/posts/unregulated-ai-use-harms-learning.html). But is there anything practical that busy instructors can do beyond writing AI policy documents? In this post, I'll sketch out my personal course structure, then lay out the source materials from the real courses and the literature.

## What I'll personally adopt
I'll start with the conclusion -- what I will personally adopt when I teach, given my reading so far.

My main focus is to restore (or, augment) pre-AI **out-of-the-classroom** [learning](https://sjonany.github.io/posts/how-to-build-mental-models-for-cs-concepts.html#mode-active), a lot of which is recently being bypassed by unguided AI usage on homework. We do this by providing **convenient, learning-inducing substitute AI**, and by making the course grade be tied to [proctored, in-person assessments](https://sjonany.github.io/posts/why-we-need-in-person-exams.html). 

### AI-specific changes
**Grading.** The grading will be heavily placed on in-person quizzes and exams. Homework will have less weight, and each problem will just be graded on completion. E.g. 20%. The motivation to do homework is that the in-person quizzes will **repeat some HW questions.** If students bypass the thinking on homework, they'll quickly learn they're only harming their in-person quiz performance.

**HW AI chat.** For students who want to use AI, they are only allowed to use a problem-specific gemini gem, and are asked to turn in the chat transcript. I will have created a class-agnostic workflow that takes in the original problem statements and the reference solution so I can scale this process. This is to make use of the "sanctioned substitute" insight from psychology. 

**HW policy.** AI usage is optional. If AI is used, students **must** (1) first provide a 30-minute first attempt that's written on **paper** before (2) using the provided HW-specific chat, then (3) turning in the chat transcript.

**Assessment content.** I'll be sure to add these flavors of tasks: (1) code review (2) plan review (3) provide test cases for this code and run them (4) conduct a runtime performance analysis of this code. This is to address the workflows that will become more common with AI-generated code.

### Non-AI changes
These are other policies that I want to adopt from [this post](https://sjonany.github.io/posts/how-to-build-mental-models-for-cs-concepts.html).

**Active engagement.** Lectures will include active worksheets, not just passive delivery. 

**Mastery.** Students can retake quizzes up to two times, but for each to be a pass, they have to earn a very high grade (E.g. >90%). See [mastery learning](https://en.wikipedia.org/wiki/Mastery_learning)

**Spaced repetition?** I'm not sure if I can afford to add additional assessments, so I'll only semi-encourage this through delayed assessments like midterms and final exams.

### Other thoughts
**AI detection.** I don't want to get into the cat-and-mouse game of detecting if students are misusing AI in the homework. If they do it and bypass the learning needed to succeed in the in-person exams, they will fail the class. That's it.

**Beyond this post.** The interventions listed in the post surprisingly feel... very hands off. We **hope** that the student will use the convenient AI substitute, and realize that if they don't do the hard thinking, they will fail the weekly quizzes. I'm curious what successful CS courses will look like a decade from now, and if we figure out interventions that are very different from the ones listed in this post.

## Actual courses
Let's first take a look at recent algorithms courses: [UW](https://courses.cs.washington.edu/courses/cse421/26sp/), [CMU](https://www.cs.cmu.edu/~yangp/15-451/), [Berkeley](https://cs170.org/), [Stanford](https://cs161-stanford.github.io/), [Princeton](https://www.cs.princeton.edu/~hy2/teaching/spring26-cos423/index.html). Here are the main findings.

### In-person unchanged
The contents of in-person exams, lectures and curriculum don't seem to have changed over the years. It's worth noting that CMU and Berkeley have oral exams and oral homework, but I have doubts on how scalable this would be for single instructors.

### Out-of-class support
What seems to change the most are the policies that shape how students interact with **homework**.

**Grades: less emphasis on non-proctored.** Proctored exams take the most weight. 4 out of 5 courses placed at least 70% weight on exams, with the exception of UW only placing 50%. Princeton and CMU don't even grade homework, or only grade based on completion.

**Homework: policy only.** The homework content does not seem to be changed. The main change seems to be in the **policy**, which mentions that AI usage is optional, and if it is used, there is a guideline on how to use it. Here's one from UW: "You are allowed to use the course approved GPT only after you have worked on the problem for at least 30 minutes." 

**Custom AI.** Only UW provided its own course-specific AI. [Here](https://chatgpt.com/share/6a4fbe58-bab4-83e8-a48c-735f0ff9807d) is a chat transcript that I used to test it. The main benefits that I saw seem to be (1) **non-disclosure** of solution: "I don't want to give away the full solution" and (2) **next-step hints**: "try comparing ... ask yourself ...  A small conceptual hint: ..." (3) **encouragement to think before re-engaging**: "Spend 15–30 minutes trying to find the counterexample yourself before asking the next question." 

In summary, homework has less grade weighting, but comes with AI guidelines to ensure that the pre-AI thinking associated with homework is not bypassed. More details in the note: [How real algorithm courses tackle AI](https://docs.google.com/document/d/1BJQCEwsqsY-2UOoGyZ_PqeUHkkqzIvHmLj9YCTbivo0/edit?tab=t.0).

## CS Literature
We just saw a couple of concrete examples, and now we will broaden our search by looking at the CS education literature. We will mainly rely on [Prather et al. (2025)](https://doi.org/10.1145/3689187.3709614), which provided a list of course changes compiled from several papers and instructor interviews. 

### Grading change
There is an increased weight on proctored exams, and less weight on unproctored assessments like homework.  

### Update curriculum
More on code review, less on syntax production.
> Educators believe **code reading** has become more important than writing code from scratch, and that higher level skills like **code testing, problem decomposition, problem understanding, and debugging** have become more essential (ES-4, ES-5). ... Developers pointed out a similar shift (DS-10), but added the need t**o critically evaluate GenAI use** and its output, **writing prompts,** and **meticulousness** as new relevant competency components

### Guide AI usage
Assume that AI will be used, and guide the usage.

**Submission.** Make clear what the policies are. E.g. Must share chat transcript if AI is used. 

**Guard-railed AI**. Harvard ([Liu et al., 2024](https://doi.org/10.1145/3626252.3630938)) built course-specific AI that used socratic method and has access to the course materials. [Here](https://docs.google.com/document/d/1632kf_uEnmK16kEShhnyF-RCQhs5q_esqCg5dK4NHXo/edit?tab=t.0) is a chat log where I played around with it. Note that [UW's custom GPT](https://chatgpt.com/share/6a4fbe58-bab4-83e8-a48c-735f0ff9807d) also is similar in spirit.

**No AI for first step.** [Güner & Er (2025)](https://doi.org/10.1007/s10639-025-13337-7) suggested that students who **code first**, then later use AI just to refine, perform better than students who start their thinking with AI. A workflow that we want to encourage, then is as follows: (1) human does the first attempt without AI before (2) starting the loop of [AI provides minimal hints, human critically reviews before asking again].

### Caveat: low epistemic quality
Note that the effectiveness of some of these interventions is not rigorously tested -- a lot of these were anecdotal, and not compared against strong baselines. See [Bauer et al. (2025)](https://doi.org/10.1007/s10648-025-10020-8) for a more detailed look at the weakness of these studies. So! Treat this list more as a brainstorming tool.

## Psych literature: AI cheating as an impulse-control problem
Let's broaden our perspective even more and look at findings from psychology! If we reframe AI cheating as a behavior that students already **intellectually** know as bad, but find it hard to **avoid in the moment**, what are some **effective interventions** from the realm of psychology that we can adopt?

### Strongest effect: convenient substitute with precommitment
The most effective intervention is to provide a sanctioned **substitute** to generic AI offerings, and provide an if-then plan ([Sheeran et al., 2024](https://doi.org/10.1080/10463283.2024.2334563); [Gollwitzer & Sheeran, 2006](https://doi.org/10.1016/S0065-2601(06)38002-1)). In the context of an algorithms course, we can provide a **custom chatbot with pedagogically-sound prompts** and **give clear HW guidelines on how to use it**. For instance, underneath **every problem**, we can give a clear instruction like this: "Start a stopwatch for 30 minutes to write your first answer on paper, then use this problem-specific course GPT (link) to check or get hints."

### Less established: Motivation
Appealing to honor codes, persuasion, or making students feel the delayed cost of cheating through frequent quizzes, doesn't seem to have as strong evidence for reducing cheating on homework. This is pretty concerning, since this seems to be where most courses concentrate their interventions.

For more details, see the note [Psychology: how to discourage ai cheating](https://docs.google.com/document/d/1urFTqBVgLdqpWHaKRGS04gJLurHlo2NsZKBaJRMm3LY/edit?tab=t.0).

## Class-specific AI
Given that providing an AI substitute is likely to be one of the more effective interventions, it's worth diving deeper into how to build one.

### Gold standards, and their approach
We previously saw how Harvard ([paper](https://doi.org/10.1145/3626252.3630938), [chat log](https://docs.google.com/document/d/1632kf_uEnmK16kEShhnyF-RCQhs5q_esqCg5dK4NHXo/edit?tab=t.0)) and [UW](https://chatgpt.com/share/6a4fbe58-bab4-83e8-a48c-735f0ff9807d) CS courses have their own chat bots. However, the effectiveness of these chat bots hasn't been studied to the level of rigor described in [Bauer et al. (2025)](https://doi.org/10.1007/s10648-025-10020-8).

We will instead look at two more rigorous studies -- from a Harvard physics course ([Kestin et al., 2025](https://doi.org/10.1038/s41598-025-97652-6)) and Google DeepMind ([LearnLM Team, 2025](https://arxiv.org/abs/2512.23633)). Both did Randomized Controlled Trials (RCTs) to show that interacting with the custom chatbot helped students obtain higher test scores with less study time, than students in a traditional active-learning class or with human tutors alone.

Here are the main components of building this solution.
1. **Main ingredient: Human-curated step-wise explanations.** It's not the AI solving the problems. Instructors create the reference solutions decomposed into well-explained steps beforehand, and the AI refers to these solutions to figure out what hints to give. 
2. **Pedagogical principles guide AI.** We have some of the principles baked into the prompts: don't cognitively overload the student. Encourage active learning. Don't give the answer, asking leading short questions. See the prompts for more details: [LearnLM](https://docs.google.com/document/d/1dqbcNVXuKQVpruFzOJHpiu-btNS341EQ9SE-xnieo8Q/edit?tab=t.0), [Kestin's](https://docs.google.com/document/d/1maVB2cWHbgZUyznbu32wLI5puC-W0HH2bHGz9kTY3dA/edit?tab=t.0) .
3. **Platform** changes might be needed to provide an interface beyond a single chat box. For instance, [Kestin et al. (2025)](https://doi.org/10.1038/s41598-025-97652-6) had separate chats for each problem substep, and clear UX to navigate between substeps and to see which has been completed vs not. The [LearnLM Team (2025)](https://arxiv.org/abs/2512.23633) study triggered the chat only when the student made a mistake on an MCQ.

### Is it practical to build?
One might think that building a high-quality class-specific AI would impose too much additional work on single instructors. This is an open problem that I would like to tackle, but here are some preliminary thoughts that make me think it's tractable. 

**Platform cost is free.** UW used custom GPT, which doesn't incur any cost to the instructor (details: [CustomGPT QnA](https://docs.google.com/document/d/1VsUm1OMCGskv-d4zTX4RZJqql12npv3d6kDY5iIkfu4/edit?tab=t.0#heading=h.375zs5wft0dd)). If your institution offers Google accounts, you can use Gemini's [gems](https://gemini.google/overview/gems/) instead. Scaffolding is implicitly baked into the static homework statement, which links each section part to a different chat link.

**Pedagogical principles** are also easy to encode -- We can just reuse the same prompts from [LearnLM Team (2025)](https://arxiv.org/abs/2512.23633) and [Kestin et al. (2025)](https://doi.org/10.1038/s41598-025-97652-6). 

**Human-curated step-wise explanations** are probably a main bottleneck. We might reduce the cost by semi-automating it with AI. E.g. "Given this human-provided final solution, and the problem statement, break this down into steps", then let human adjust the steps.

**Evaluation as the hidden cost.** Evaluation of quality is harder, but I suspect we might automate some steps that can produce a decent evaluation pipeline, and a self-improving pipeline that provides a good result. E.g. for this homework problem, generate 10 common student responses, evaluate yourself, self-improve your prompt, .... This will impose some monetary cost on the instructor, TBD on how much.

So, the main cost will most likely lie in the evaluation / self-improvement workflow and the step-wise explanation creation. It will be an interesting project to see how much of these can be automated, and various practical integration patterns to accommodate instructors of varying bandwidth. TBD for a future post! 

## References
- Bauer, E., Greiff, S., Graesser, A. C., Scheiter, K., & Sailer, M. (2025). Looking Beyond the Hype: Understanding the Effects of AI on Learning. *Educational Psychology Review, 37*(2). https://doi.org/10.1007/s10648-025-10020-8
- Gollwitzer, P. M., & Sheeran, P. (2006). Implementation intentions and goal achievement: A meta-analysis of effects and processes. *Advances in Experimental Social Psychology, 38*, 69–119. https://doi.org/10.1016/S0065-2601(06)38002-1
- Güner, H., & Er, E. (2025). AI in the classroom: Exploring students' interaction with ChatGPT in programming learning. *Education and Information Technologies, 30*, 12681–12707. https://doi.org/10.1007/s10639-025-13337-7
- Jonany, S. (2026). Unregulated AI use harms learning. https://sjonany.github.io/posts/unregulated-ai-use-harms-learning.html
- Kestin, G., Miller, K., Klales, A., Milbourne, T., & Ponti, G. (2025). AI tutoring outperforms in-class active learning: an RCT introducing a novel research-based design in an authentic educational setting. *Scientific Reports, 15*, 17458. https://doi.org/10.1038/s41598-025-97652-6
- LearnLM Team, Google (2025). AI tutoring can safely and effectively support students: An exploratory RCT in UK classrooms. *arXiv* preprint arXiv:2512.23633. https://arxiv.org/abs/2512.23633
- Liu, R., Zenke, C., Liu, C., Holmes, A., Thornton, P., & Malan, D. J. (2024). Teaching CS50 with AI: Leveraging Generative Artificial Intelligence in Computer Science Education. In *Proceedings of the 55th ACM Technical Symposium on Computer Science Education (SIGCSE 2024).* ACM. https://doi.org/10.1145/3626252.3630938
- Prather, J., Leinonen, J., Kiesler, N., Gorson Benario, J., Lau, S., MacNeil, S., Norouzi, N., Opel, S., Pettit, V., Porter, L., Reeves, B. N., Savelka, J., Smith, D. H., Strickroth, S., & Zingaro, D. (2025). Beyond the Hype: A Comprehensive Review of Current Trends in Generative AI Research, Teaching Practices, and Tools. In *2024 Working Group Reports on Innovation and Technology in Computer Science Education (ITiCSE-WGR '24).* ACM. https://doi.org/10.1145/3689187.3709614 (arXiv:2412.14732)
- Sheeran, P., Listrom, O., & Gollwitzer, P. M. (2024). The when and how of planning: Meta-analysis of the scope and components of implementation intentions in 642 tests. *European Review of Social Psychology, 36*(1), 162–194. https://doi.org/10.1080/10463283.2024.2334563

Deep dive notes
- [Psychology literature: How to discourage AI cheating](https://docs.google.com/document/d/1urFTqBVgLdqpWHaKRGS04gJLurHlo2NsZKBaJRMm3LY/edit?tab=t.0)
- [How real algorithm courses tackle AI](https://docs.google.com/document/d/1BJQCEwsqsY-2UOoGyZ_PqeUHkkqzIvHmLj9YCTbivo0/edit?tab=t.0)
- [LearnLM prompt](https://docs.google.com/document/d/1dqbcNVXuKQVpruFzOJHpiu-btNS341EQ9SE-xnieo8Q/edit?tab=t.0)
- [Kestin's prompt](https://docs.google.com/document/d/1maVB2cWHbgZUyznbu32wLI5puC-W0HH2bHGz9kTY3dA/edit?tab=t.0) 
- [CustomGPT QnA](https://docs.google.com/document/d/1VsUm1OMCGskv-d4zTX4RZJqql12npv3d6kDY5iIkfu4/edit?tab=t.0#heading=h.375zs5wft0dd)
- [UW's custom GPT chat log](https://chatgpt.com/share/6a4fbe58-bab4-83e8-a48c-735f0ff9807d)
- [Harvard's CS 50 chat log](https://docs.google.com/document/d/1632kf_uEnmK16kEShhnyF-RCQhs5q_esqCg5dK4NHXo/edit?tab=t.0)

*Comment via: [medium](https://medium.com/p/71086c2b6372), [substack](https://stephenjonany.substack.com/p/ai-proofing-a-cs-course), [linkedin](https://www.linkedin.com/pulse/ai-proofing-cs-course-stephen-jonany-dgpgc/)*
