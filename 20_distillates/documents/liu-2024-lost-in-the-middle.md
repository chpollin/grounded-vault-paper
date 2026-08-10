---
type: distillate
source-type: document
representation: "[[10_markdown/documents/liu-2024-lost-in-the-middle]]"
topics: ["[[Architecture]]", "[[Agentic Workflow]]"]
status: grounded
checked:
  validation: 2026-08-10
created: 2026-08-10
updated: 2026-08-10
---

# Distillate: Lost in the Middle: How Language Models Use Long Contexts

The source shows by controlled experiment that a language model's use of its input context depends on where in the context the relevant information sits, and that more context is not reliably better.

## Core statements

- The source reports that model performance degrades significantly when the position of the relevant information changes, and that performance is often highest when that information stands at the beginning or the end of the input context. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b01]] ^s1

- The source states that its experiments vary the input context size and the position of the relevant information within it, and that a model robustly using long contexts would show performance minimally affected by that position. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b04]] ^s2

- The source reports a U-shaped performance curve with a primacy and a recency bias, and reports that GPT-3.5-Turbo answering from relevant information placed in the middle of its context performs below its own closed-book performance of 56.1%. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b06]] ^s3

- The source states that models often perform identically to their extended-context counterparts, so a larger context window does not by itself mean better use of the context. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b23]] ^s4

- The source builds its multi-document question answering task so that exactly one of the k input documents contains the answer and the remaining documents are distractors. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b15]] ^s5

- The source draws its questions from NaturalQuestions-Open, using the 2655 queries whose annotated long answer is a paragraph, with Wikipedia passages of at most 100 tokens as the documents. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b16]] ^s6

- The source states that it modulates the position of the relevant information by reordering the documents and the context length by adding or removing documents that do not contain the answer. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b18]] ^s7

- The source reduces the question to a synthetic key-value retrieval task over JSON key-value pairs of random UUIDs, in order to test the bare ability to retrieve a matching token from the input context without linguistic confounders. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b25]] ^s8

- The source reports that Claude-1.3 and Claude-1.3 (100K) perform nearly perfectly on the key-value retrieval task at all evaluated context lengths, while other models struggle at 140 or 300 key-value pairs even though the task only requires exact matching. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b29]] ^s9

- The source reports that GPT-3.5-Turbo, GPT-3.5-Turbo (16K) and MPT-30B-Instruct perform worst when the relevant key-value pair sits in the middle of the input context. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b30]] ^s10

- The source reports that the encoder-decoder model Flan-UL2 is robust to the position of the relevant information within its 2048-token training-time context window, at 1.9% absolute difference between best and worst case, and begins to degrade in the middle once sequences exceed that length. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b34]] ^s11

- The source reports that query-aware contextualization, placing the query before as well as after the data, lifts all models to near-perfect performance on the key-value retrieval task at 75, 140 and 300 pairs. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b36]] ^s12

- The source reports that without query-aware contextualization the worst-case key-value performance is 45.6%, and that query-aware contextualization barely changes the performance trends of the multi-document question answering task. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b37]] ^s13

- The source reports that MPT-30B shows the U-shaped curve with and without instruction fine-tuning, and that fine-tuning narrows the gap between best and worst case from nearly 10% to around 4%. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b39]] ^s14

- The source reports that the U-shaped curve appears only in sufficiently large models, with the 7B Llama-2 models solely recency-biased while the 13B and 70B models show the curve. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b41]] ^s15

- The source reports that in a retriever-reader setup on NaturalQuestions-Open, reader performance saturates long before retriever performance does, and that going beyond 20 retrieved documents improves the reader by only 1.5% for GPT-3.5-Turbo and 1% for Claude-1.3 while lengthening the input context. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b44]] ^s16

- The source states that longer input contexts are a trade-off, in that more information may help the task while also increasing the content the model must reason over, potentially decreasing accuracy. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b12]] ^s17

- The source proposes that a claim of robust long-context use requires showing that performance is minimally affected by the position of the relevant information, for instance as a minimal difference between best and worst case. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b13]] ^s18

- The source connects the observed U-shaped curve to the serial-position effect known from psychology. [[10_markdown/documents/liu-2024-lost-in-the-middle#^b45]] ^s19

## Terms

- **Primacy bias**: the tendency of a model to use relevant information better when it stands at the very beginning of the input context [[10_markdown/documents/liu-2024-lost-in-the-middle#^b06]]
- **Recency bias**: the tendency of a model to use relevant information better when it stands at the end of the input context [[10_markdown/documents/liu-2024-lost-in-the-middle#^b06]]
- **Query-aware contextualization**: placing the query both before and after the data to be processed, so that a decoder-only model can attend to the query while contextualizing that data [[10_markdown/documents/liu-2024-lost-in-the-middle#^b35]]

## Open questions

- The source measures accuracy by substring match of an annotated answer and does not settle how the positional effect behaves under a stricter measure of answer quality.
- The source shows the effect on retrieval and question answering and leaves open whether the same curve governs tasks that must combine information from several positions at once.
- The source names reranking and list truncation as promising remedies without measuring either.

## Appraisal

The paper is the standard reference for positional sensitivity in long contexts, and its controlled design is what earns it that standing, since it varies one thing at a time against a fixed answer set instead of inferring the effect from a benchmark score. For this vault the finding bears directly on how a source is handed to an agent: a long, undifferentiated context is not equivalent to a short, targeted one, and an anchor that points a later run at a specific passage is doing work that a large context window does not do for free. The evaluated models are those of 2023, so the concrete numbers age; the evaluation protocol the paper proposes, showing a minimal difference between best-case and worst-case position, is what survives and is the part this vault would apply to a current model. The synthetic key-value task deliberately strips out language, which makes it a clean test of retrieval and a weak proxy for the reading that a distillation step actually performs.

## Related

- [[20_distillates/documents/gao-2023-llms-generate-text-with-citations]]
