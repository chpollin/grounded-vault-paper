---
type: assertion
topics: ["[[Verification]]"]
status: grounded
checked: {}
grounding:
  - "[[20_distillates/publications/rashkin-2023-measuring-attribution#^s2]]"
  - "[[20_distillates/publications/rashkin-2023-measuring-attribution#^s8]]"
  - "[[20_distillates/documents/gao-2023-llms-generate-text-with-citations#^s7]]"
  - "[[20_distillates/documents/gao-2023-llms-generate-text-with-citations#^s8]]"
contested-with: []
created: 2026-08-10
updated: 2026-08-10
---

# Attribution is separate from correctness

## Statement

Whether an identified source supports a generated statement is judged on its own, and the framework that judges it declines any absolute verdict on the factuality of the statement. Automatic evaluation of generated text with citations follows the same cut and scores correctness, meaning agreement with a ground truth answer, on a different axis from citation quality, meaning support of the answer by the cited passages. An answer can therefore be accurate while its citations fail to carry it, and it can be well cited while being wrong.

## Support

- [[20_distillates/publications/rashkin-2023-measuring-attribution#^s2]] — defines attribution as the accurate use of source documents to support generated text, which fixes the relation as one between text and source.
- [[20_distillates/publications/rashkin-2023-measuring-attribution#^s8]] — records that the framework avoids absolute judgments about the factuality of utterances, which keeps truth outside the attribution verdict.
- [[20_distillates/documents/gao-2023-llms-generate-text-with-citations#^s7]] — defines correctness as whether the answer is accurate and covers all aspects of interest.
- [[20_distillates/documents/gao-2023-llms-generate-text-with-citations#^s8]] — defines citation quality as whether the answer is well supported by the cited passages, which is the second and independent axis.

## Related

- [[30_assertions/generated-citations-often-fail-to-support-their-sentences]]
- [[30_assertions/historical-method-separates-origin-check-from-credibility]]
