---
type: assertion
topics: ["[[Provenance]]"]
status: grounded
checked: {}
grounding:
  - "[[20_distillates/documents/tei-p5-critical-apparatus#^s12]]"
  - "[[20_distillates/documents/tei-p5-critical-apparatus#^s16]]"
  - "[[20_distillates/documents/tei-p5-critical-apparatus#^s17]]"
  - "[[20_distillates/documents/tei-p5-critical-apparatus#^s22]]"
  - "[[20_distillates/documents/tei-p5-critical-apparatus#^s23]]"
contested-with: []
created: 2026-08-10
updated: 2026-08-10
---

# The critical apparatus binds each reading to its witnesses

## Statement

In the TEI encoding of a critical apparatus a given reading is associated with the set of witnesses attesting it by listing those witnesses in the wit attribute on the rdg or lem element. That attribute holds a space-delimited list of one or more pointers indicating the attesting witnesses, and each witness carries a unique siglum supplied with the global xml:id attribute, which is the identifier used elsewhere to refer to that witness. A list of all identified witnesses is normally supplied in the front matter of the edition or in the sourceDesc element of its header. The binding is differentiated by role, since wit identifies the physical entity in which the reading is found, hand refers to the agent responsible for inscribing it there, and source indicates the scholar responsible for asserting that the reading exists in that physical entity.

## Support

- [[20_distillates/documents/tei-p5-critical-apparatus#^s12]] — gives the wit attribute as a list of pointers to the attesting witnesses
- [[20_distillates/documents/tei-p5-critical-apparatus#^s16]] — separates carrier, inscribing agent and asserting scholar across wit, hand and source
- [[20_distillates/documents/tei-p5-critical-apparatus#^s17]] — states the binding of a reading to its set of witnesses on rdg or lem
- [[20_distillates/documents/tei-p5-critical-apparatus#^s22]] — supplies the witness list in the front matter or the sourceDesc element as the register the pointers resolve against
- [[20_distillates/documents/tei-p5-critical-apparatus#^s23]] — supplies the unique siglum as the identifier that makes the pointer resolvable

## Related

- [[30_assertions/prov-models-entities-activities-agents]]
