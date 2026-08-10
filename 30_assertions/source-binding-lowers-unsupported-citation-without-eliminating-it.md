---
type: assertion
topics: ["[[Verification]]"]
status: grounded
checked: {}
grounding:
  - "[[20_distillates/documents/fabricated-citations-chatgpt-2023#^s2]]"
  - "[[20_distillates/documents/fabricated-citations-chatgpt-2023#^s3]]"
  - "[[20_distillates/documents/legal-ai-research-tools-hallucination-2025#^s1]]"
contested-with: []
created: 2026-08-10
updated: 2026-08-10
---

# Source binding lowers the rate of unsupported citation without eliminating it

## Statement

Models that generate references without being bound to a retrieved corpus invent a large share of them. Of the works cited in papers written by GPT-3.5, 55% do not exist as works that have been published, presented, posted or otherwise publicly disseminated, and of the works cited by GPT-4 the share is 18%. Commercial legal research tools that generate over a retrieved authoritative corpus hallucinate between 17% and 33% of the time, which is a reduction relative to the general purpose chatbot GPT-4 and still a substantial residual rate.

## Support

- [[20_distillates/documents/fabricated-citations-chatgpt-2023#^s2]] — supplies the 55% fabrication rate for GPT-3.5 together with the definition of a fabricated work as one never publicly disseminated.
- [[20_distillates/documents/fabricated-citations-chatgpt-2023#^s3]] — supplies the 18% fabrication rate for GPT-4, which shows the failure persists across model versions without source binding.
- [[20_distillates/documents/legal-ai-research-tools-hallucination-2025#^s1]] — supplies the 17% to 33% hallucination range of three retrieval based commercial systems and the comparison that establishes the reduction against GPT-4.

## Related

- [[30_assertions/resolvable-citation-without-support-is-a-distinct-error-class]]
- [[30_assertions/llm-summaries-broaden-the-scope-of-findings]]
