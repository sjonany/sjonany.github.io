# Improving RAG Performance
*Published 2025-09-10*

**TL;DR.** Read how [Anthropic did it](https://www.anthropic.com/news/contextual-retrieval), and for more tips, read Chapter 6 of the [AI engineering book](https://www.amazon.com/AI-Engineering-Building-Applications-Foundation/dp/1098166302). I’m just condensing tips that I’ll personally use.

I have been looking into various RAG resources, from Llama Index CEO [1], Anthropic [2] and this O’Reilly AI engineering book [3]. Here are the various ways you can improve your RAG pipeline. I organize them in the order in which I would personally try them, by weighing the foreseen benefit and the implementation and monetary cost.

**Table of content**

1. [Use a better embedder](#1-use-a-better-embedder)
2. [Rewrite your query](#2-rewrite-your-query)
3. [Improve data preparation](#3-improve-data-preparation)
4. [Set up evaluation framework](#4-set-up-evaluation-framework)
5. [Improve chunking strategy](#5-improve-chunking-strategy)
6. [Enrich the chunk](#6-enrich-the-chunk)
7. [Add a re-ranking](#7-add-a-re-ranking-step)
8. [Add keyword-based retriever](#8-add-keyword-based-retriever)

## Low-hanging fruits

### **1. Use a better embedder**

Anthropic [3] recommended [Gemini](https://ai.google.dev/gemini-api/docs/embeddings) and [Voyager](https://docs.voyageai.com/docs/embeddings).

### **2. Rewrite your query**

If you have a crappy query like “This doesn’t work” and feed it directly to the RAG, then you lose all hope in getting meaningful matches. [2] suggested rewriting the user query first. Here are more snippets from the book:

> **Example scenario**
>
> User: When was the last time John Doe bought something from us?
> AI: John last bought a Fruity Fedora hat from us two weeks ago, on January 3, 2030.
> User: How about Emily Doe?
>
> The last question, “How about Emily Doe?”, is ambiguous without context. If you use this query verbatim to retrieve documents, you’ll likely get irrelevant results. You need to rewrite this query to reflect what the user is actually asking. The new query should make sense on its own. In this case, the query should be rewritten to “When was the last time Emily Doe bought something from us?”
>
> **Example prompt**
> “Given the following conversation, rewrite the last user input to reflect what the user is actually asking”.

### **3. Improve data preparation**

From [1] you can supposedly improve your PDF-to-text performance using [LlamaParse](https://www.llamaindex.ai/llamaparse). The benefit of this step depends on how complicated your PDF is. If your PDFs are simple, then this step is probably not that important.

## More expensive options

**Preface.** Everything below here I would not do unless I have invested in an evaluation framework, because they’re more expensive, and so you would want to invest in keeping these additions only if you have data points to show that (1) your performance currently sucks and (2) these heavy investments do help in a significant way

### **4. Set up evaluation framework**

Set up a robust evaluation framework. Track precision and recall. You can use AI as a judge to auto-generate a dataset for you like so: Start with a bunch of queries and a fixed document library. For each query, use AI to label which docs are relevant vs not. With an evaluation framework, you can gain more confidence in your changes.

### **5. Improve chunking strategy**

LlamaIndex [1] recommended starting with per-page chunking as a baseline, because in some media, information is optimized to not be broken across page boundaries. [2] recommended the following:

- **Creative chunks.** E.g. QnA
    Specific documents might also support creative chunking strategies. For example, there are splitters developed especially for different programming languages. Or, Q&A documents can be split by each question and answer pair.
- **Add overlaps**
    When a document is split into chunks without overlap, the chunks might be cut off in the middle of important context, leading to the loss of critical information. Overlapping ensures that important boundary information is included in at least one chunk. If you set the chunk size to be 2,048 characters, you can perhaps set the overlapping size to be 20 characters.
- **Tweak the chunk size.** For this, you just have to experiment with your evaluation framework.

### **6. Enrich the chunk**

Instead of just using a chunk of raw text as the vector store key, Anthropic [3] suggested prepending chunk-specific explanatory context.

E.g.

> original_chunk = “The company’s revenue grew by 3% over the previous quarter.”
>
> contextualized_chunk = “This chunk is from an SEC filing on ACME corp’s performance in Q2 2023; the previous quarter’s revenue was $314 million. The company’s revenue grew by 3% over the previous quarter.”

Here is their example prompt

> <document>
> {{WHOLE_DOCUMENT}}
> </document>
> Here is the chunk we want to situate within the whole document
> <chunk>
> {{CHUNK_CONTENT}}
> </chunk>
> Please give a short succinct context to situate this chunk within the overall document for the purposes of improving search retrieval of the chunk. Answer only with the succinct context and nothing else.

- Warning: This is **not** just adding a summary of the chunk nor the document — the prefix is a function of both.

> It is worth noting that other approaches to using context to improve retrieval have been proposed in the past. Other proposals include: [adding generic document summaries to chunks](https://aclanthology.org/W02-0405.pdf) (we experimented and saw very limited gains), [hypothetical document embedding](https://arxiv.org/abs/2212.10496), and [summary-based indexing](https://www.llamaindex.ai/blog/a-new-document-summary-index-for-llm-powered-qa-systems-9a32ece2f9ec) (we evaluated and saw low performance). These methods differ from what is proposed in this post.

- You can also add more context. [2] suggested adding keywords, or questions that this chunk might answer (AI-generated, of course).
    For example, the article on how to reset your password can be augmented with queries like “How to reset password?”, “I forgot my password”, “I can’t log in”, or even “Help, I can’t find my account”.
- Note: This same enriched chunk, not the raw chunk is also what’s passed to the BM25 index.

### 7. Add a re-ranking step

From Anthropic [3], you can divide your retrieval into multiple phases: (1) **A high-recall**, cheap retrieval phase from possibly multiple approaches — e.g. vector store and BM25 followed by (2) A more **accurate, more expensive re-ranking** step. As a baseline, [2] mentioned RRF [4], but Anthropic [3] mentioned there are commercial solutions from [Cohere](https://cohere.com/rerank) and [Voyage](https://docs.voyageai.com/docs/reranker). Finally, you can add custom re-ranking logic if you have additional metadata like each source’s trustworthiness, and train your own ranker using traditional ML methods.

### **8. Add keyword-based retriever**

Vector-based retrievers can surprisingly fail at matching exact keywords like exact error codes, or long scientific names. Anthropic [3] recommended using BM25-based retriever in addition to the vector-based retriever, then merging the results using a re-ranking step.

## References

[1] [Building Production RAG Over Complex Documents](https://www.youtube.com/watch?v=dI_TmTW9S4c) — Jerry Liu, Co-founder and CEO, LlamaIndex

[2] [AI engineering](https://www.amazon.com/AI-Engineering-Building-Applications-Foundation/dp/1098166302) Chapter 6 — Chip huyen

[3] [Introducing Contextual Retrieval](https://www.anthropic.com/news/contextual-retrieval) — Anthropic

[4] [https://cormack.uwaterloo.ca/cormacksigir09-rrf.pdf](https://cormack.uwaterloo.ca/cormacksigir09-rrf.pdf)
