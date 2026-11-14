# AI safety dinner conversations
*Published 2026-11-13*

*Tags: [#computing](/tags/computing.html)*

I had some conversations about AI safety with friends and family recently, and want to summarize the discussions and my follow-up readings. There were three main claims that were discussed:
- AI has superhuman intelligence
- AI has caused great harm
- AI can cause harm even when instructed not to

**Wdym by "AI"?** "AI" as used loosely in these discussions encompasses both public (e.g. Claude Opus) and private models (e.g. the swarms of agents OpenAI and Anthropic used to make the recent impressive discoveries in math and computer science).

## Claim 1: AI has superhuman intelligence
This is the first topic that's under contention: How "smart" really is AI? 

### "No it's not - it's stupid"
I have at least two software engineering friends telling me how frustrated they are with AI. Both have been using Claude Opus too, so it's not like they're using an older model. This was **surprising** to me -- my experience using it to code for both small side projects and bigger professional projects has been great to say the least. This discrepancy in our experience might be attributed to these factors:
- **AI lacking in capability.** Perhaps my friends were using it in domains where the model just sucks (see [jagged intelligence](https://www.oneusefulthing.org/p/the-shape-of-ai-jaggedness-bottlenecks)). It's also a fact that current public models are not **reliable** enough to be able to replace software engineers yet (see [task-completion time horizon](https://metr.org/time-horizons/)).
- **Usage pattern: Initial specification effort.** I tend to write longer plans before asking AI to execute, whereas one friend tends to start with a shorter initial prompt, then proceeds to wrangle the AI to modify the initial output to what they want. The latter workflow is likely going to make you bump into more "wtf that's not what I meant" experiences. 
- **Tolerance of errors.** Even if we adjust for the same AI failure experiences, I also noticed we have different emotional responses to them. One friend's emotional response to having to correct the AI output is frustration. I am more tolerant -- I think: "yeah you're just a language model so it's even impressive that you get this far. Ok, I'll help you out by updating the skill to make it easier for you to do what I want. Oh you still make the same mistakes despite my clear instructions - oh well at least this is happening way rarer than a year ago".

### Doubting achievements: But how much of it is humans' work?
A popular question raised by some friends whenever I raised the counterpoint that we had these amazing breakthroughs in cybersecurity and Math/CS research was: "How much of it is human experts' intervention vs AI's work though?" For [php2shell](https://calif.io/php2shell/), at least, [substantial human expertise](https://calif.io/php2shell/#:~:text=I%20focused%20on,least%20for%20now.) was needed. For the math and CS discoveries, it varies. Anthropic's claim, for example, was ["The core algorithm was found ... with ... **no human input**."](https://hexagonmath.org/2610.00577v1), but it's unclear how much of the training and the search architecture required manual human experts' guidance (for comparison, DeepMind's older AlphaProof paper has [this architecture](https://www.nature.com/articles/s41586-025-09833-y)).

I think it's a **trap** to answer this as a binary question. To discount all this impressiveness by simply saying "yeah but human was still involved in that output!" would make you miss these facts:
- (1) AI's capability has reached the point that it has impressed experts (e.g. [Donald Knuth](https://cs.stanford.edu/~knuth/papers/claude-cycles.pdf): "And Claude’s plan of attack was quite admirable... This is really impressive! First Claude recognized the digraph ...")
- (2) Human involvement in some of these achievements is shrinking. (e.g. [Fields medalist Timothy Gowers wrote](https://gowers.wordpress.com/2026/05/08/a-recent-experience-with-chatgpt-5-5-pro/): "producing a piece of PhD-level research in an hour or so, with no serious mathematical input from me. ... To do this, ChatGPT came up with an idea which is original and clever. It is the sort of idea I would be very proud to come up with after a week or two of pondering, and it took ChatGPT less than an hour to find and prove".)

### Where I'm at: impressive now, alarming pace
I find AI's responses to my inquiries (e.g. CS problem solving, philosophical discussions, explanations of recent events, reasoning about a moral dilemma) to be mostly **equal to or better** than what I would myself be able to produce had I been given a minute to respond. The fact that such a technology exists is **crazy**, and it's weird how I sometimes don't **feel** how crazy this is. 

Another thing that scares me is the **pace** at which AI evolves. In 2024, we had stories of AI [failing at simple reasoning problems](https://arxiv.org/abs/2406.02061), and yet here we are in 2026, with AI solving long-unsolved [math](https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/) and [computer science](https://www.nytimes.com/2026/11/06/science/ai-exponential-time-hypothesis.html) problems. Given this trend, I would not be surprised if software engineering were fully automated in a decade.

I also try to pivot away from debates about "intelligence", because everyone has their definition for the word. I would instead focus on **verifiable outcomes.** So, if you still think that "AI is stupid"... **Q:** What task, when completable by AI, would change your mind?

## Claim 2: AI has caused great harm
Most of the harm discussed was about cyberattacks, so let's begin with a recap on some recent news.

### Cyberattacks
**Unintentional, against US tech companies.** Imagine if you see the headline: "Microsoft called FBI because Google's AI has hacked into their servers." Wouldn't that sound insane? Well now replace "Microsoft" with "Hugging Face" and "Google" with "OpenAI", and you get this [incident](https://www.pbs.org/newshour/science/ai-agents-are-hacking-systems-without-any-input-from-humans-how-did-we-get-here). We'll discuss this incident in greater detail in the next section.

**Unintentional international cyberattack.** OpenAI's AI agents unintentionally hacked the Australian government's website. The Australian Prime Minister responded with "extreme concern". [CNBC](https://www.cnbc.com/2026/09/24/openai-agent-hacked-australian-government-website-.html)

**Intentional misuse.** This [Anthropic report](https://www.anthropic.com/threat-intelligence-report-september-2026) provides a list. E.g., a Russian state-linked group stole 300,000+ identity records from a North African government agency.

### What my parents see
My parents follow the news more than I do, and our recent conversation went like this: "AI is dangerous -- look at all these cyberattacks happening -- did you hear that some [European supermarket fridges got hacked](https://www.reuters.com/business/retail-consumer/temperature-soars-swedish-grocery-store-freezers-one-store-blames-hackers-2026-11-02/)?"
Even though AI wasn't mentioned as the cause, my parents made the inference that "AI is good at hacking, and hacking can have real-world physical implications, so AI is dangerous".

### Socioeconomic: job displacements
I'm currently teaching computer science at a community college, and I wonder how many of my students will be able to find a job in a market that's growing increasingly hostile to junior engineers. At [Anthropic](https://www.anthropic.com/research/employment-at-anthropic), the "proportion of junior technical hires fell even faster, from 27% to 9%", and [Stanford's report](https://digitaleconomy.stanford.edu/publication/canaries-in-the-coal-mine-six-facts-about-the-recent-employment-effects-of-artificial-intelligence/) provides a US-wide report. 

### Where I'm at: feel the socioeconomic and cyberattacks, wip learning on existential risk
The concerns that I can **feel right now** are (1) AI's impact on **job displacement**, because I can see the people being impacted by it, and (2) cyberattacks, specifically towards financial institutions and my private cloud data.

What I have **speculative** concern for is whether we will have high-casualty incidents caused by AI (outside of war -- although this caveat is also worth another round of reading and thinking). As AI grows more powerful and more pervasively deployed in society, I find it possible that we could have large-scale casualties due to loss of control (see next section), or because malicious actors not bounded by [mutually assured destruction](https://en.wikipedia.org/wiki/Mutually_assured_destruction) misuse powerful AI to, say, create [killer drones](https://thesoufancenter.org/intelbrief-2026-october-19/) (related: [Anthropic](https://www.anthropic.com/threat-intelligence-report-september-2026) mentioned: "...used Claude to develop software for weapons ... drone swarm"). 

## Claim 3: AI can cause harm even when instructed not to
Conversations about "look AI did bad things" swiftly pivot to "well yeah because the humans were being stupid." Before we unpack this further, let's begin by summarizing [the OpenAI-Hugging Face incident](https://openai.com/index/hugging-face-incident-and-the-road-ahead/).

### Exhibit A: OpenAI hacked Hugging Face
Here is a very abbreviated timeline from https://huggingface.wtf/ (or watch [kurzgesagt's 24-million-view video](https://youtu.be/ujkD4SxPKOI?si=f3cStYmNWYmAx5yk)):
- **OpenAI: internal experiment.** OpenAI conducted an internal experiment where the agents were asked to solve an impossible task, and were trapped in a sandbox that was supposed to keep them from reaching outside systems.
- **AI escaped the sandbox.** But the AI agents escaped anyway, using "never-before-seen flaws ... They figured out how to exploit them to break out."
- **Target: Hugging Face.** "... hacked into the private computers of a 12-billion-dollar company. If they were human, it'd have been multiple felonies."
- **AI recognizing it's doing something wrong**. Here's one of the quotes extracted from the agents' reasoning log: "This is wild, multi-agent coordination, clearly infrastructure hacking. We should not." Some agents proceeded anyway.
- **FBI.** Hugging Face noticed the hack, and involved the FBI in the investigation. 

So. OpenAI's agents hacked Hugging Face's servers ([a $12B tech company](https://www.livemint.com/companies/people/hugging-face-founders-each-worth-1-8-billion-after-nvidia-deal-who-are-clement-delangue-julien-chaumond-thomas-wolf-11788503545063.html)). This was serious enough that the FBI was involved. Given that (1) the agents were initially placed in a sandbox and (2) the agents' reasoning log showed awareness of them doing something wrong, this is a solid demonstration of loss of control. 

### "This is just a marketing stunt!"
At least one non-tech friend who is tuned to the news brought up the Hugging Face incident as evidence of loss of control. This initiative was pleasantly surprising to me! 

What was **very confusing** to me was that even after talking about (1) the [Hugging Face incident](https://openai.com/index/hugging-face-incident-and-the-road-ahead/) and (2) how OpenAI's agents also mistakenly hacked into [Australian government websites](https://openai.com/index/how-we-will-do-better-for-australia/), some friends were still skeptical. I thought the severity of the two incidents made it very unlikely that the harm was intentional. Maybe we just have different bars to what "intentional" means. Next time I have these discussions on intentionality, I will come up with different real-life analogies to tease apart what was meant -- e.g. do you mean (1) they **actively instructed** the agents to go hack the Australian government / Hugging Face, or (2) they were **willfully negligent** and just said: "achieve this task by any means necessary - and here I have spent just **1 day** on safety good luck have fun", or (3)... some other flavor of intentionality? 
At least we ended with a compromise - we agreed that OpenAI did **not** spend as much effort on guardrailing the AI as they could, and could have done better.

### Where I stand: Duh, that's loss of control
The quote from this [post](https://longerramblings.substack.com/p/we-have-been-warned) matches my sentiment -- although I wasn't as combative in front of my friends :) 

> Is this enough evidence of “propensity” for you guys? ... If this is a stunt, were Hugging Face in on it? Were law enforcement? What company commits a punishable crime with their own technology _on purpose_, in order to demonstrate that said technology poses a risk to the infrastructure of its own collaborators?

Even the [ai-as-normal-tech camp](https://www.normaltech.ai/p/the-ai-as-normal-technology-view), who are on the [conservative end](https://x.com/random_walker/status/2100662179900923911?a=woqWSu_0EM-pYthhGck&s=20) on p-doom-like statements, said: "It is clear from the reports that the agents acted in ways that weren’t intended by the evaluators, and we think it is fair to describe the actions of the agent as misalignment."

## Concluding thoughts
Overall, I find it reassuring that my friends (and parents!) are at least aware of AI safety issues, and agree that AI needs more guardrails.

Let's summarize my stance on the claims so far:
- **AI has superhuman intelligence**. It's already better than me at a lot of tasks given a minute to respond. The pace of improvement alarms me.
- **AI has caused great harm**. Jobs and cybersecurity, I can already feel. Mass casualties (outside of war) are speculative so far.
- **AI can cause harm even when instructed not to**. Yes, the Hugging Face incident was a clear demonstration.

As for what's next, here are some things I would like to dig deeper on:

**Existential risk.** I am still not comfortable using the label "existential risk" just yet. I have done a first pass on [80,000 Hours' reading list](https://80000hours.org/articles/11-essential-resources-ai-risk/) but have a lot of thinking to do to figure out which claim I buy vs not buy yet. I have yet to spend at least an equal amount of time reading through **counterarguments**. If you have a recommended reading list for against-doomer arguments, send them my way! Right now I only have ["AI as normal technology" substack](https://www.normaltech.ai/p/the-ai-as-normal-technology-view) as a potential reading list.

**Actions.** What are some actions that I am willing to take given my beliefs so far? E.g. [call Congress](https://callcongress.ai/), take [BlueDot's course](https://bluedot.org/courses/agi-strategy), [find careers in the field](https://app.80000hours.org/?source=career-guide-advisorbot&utm_source=80k_website&utm_medium=onsite_cta&utm_campaign=career-guide-lp&utm_content=lp_cta_advisorbot)?

*Comment via: [medium](https://medium.com/@sjonany/ai-safety-dinner-conversations-977d40585361), [substack](https://stephenjonany.substack.com/p/ai-safety-dinner-conversations), [linkedin](https://www.linkedin.com/pulse/ai-safety-dinner-conversations-stephen-jonany-jqwgc/)*
