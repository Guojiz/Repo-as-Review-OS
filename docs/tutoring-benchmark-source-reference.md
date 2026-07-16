# DeepTutor Benchmark Reference

GitLearnOS uses [HKU DeepTutor](https://github.com/HKUDS/DeepTutor) as its capability benchmark, not as a code or product-shape template.

Primary references:

- [DeepTutor official repository](https://github.com/HKUDS/DeepTutor)
- [DeepTutor technical report, arXiv:2604.26962](https://arxiv.org/abs/2604.26962)
- [DeepTutor official site](https://deeptutor.info/)

## Learning-critical ideas adopted

The public report and repository emphasize:

- static knowledge grounding plus dynamic learner memory;
- a closed loop between grounded problem solving and calibrated question generation;
- shared personalization across learning workflows;
- inspectable memory and evidence provenance;
- skills as an extension surface;
- student-centric evaluation.

GitLearnOS implements lightweight analogues:

```text
source records
+ evidence-linked learner profile
+ knowledge gaps
+ session and review skills
+ observable scoring
+ Git history
```

## Explicit non-equivalence

GitLearnOS does not implement DeepTutor's full runtime, TutorBot/Partners, multiple RAG engines, multi-agent research, application surfaces, memory graph, server, database, or benchmark infrastructure.

Claims should use this wording:

```text
capability-benchmarked against DeepTutor
lightweight adaptation of learning-loop ideas
not a reproduction or parity claim
```

## Lightweight evaluation mapping

| Research-facing question | Repository-level check |
|---|---|
| Is the answer grounded? | source access state and inspected portion are recorded |
| Is personalization evidence-based? | profile/gap claims link to reviews or sessions |
| Does practice expose a real gap? | review links goal, gap, model, and source |
| Does the loop close? | result changes score, state, and next action |
| Can the learner inspect it? | canonical Markdown files and Git history remain editable |

This document records design provenance; it does not bundle or redistribute DeepTutor source material or benchmark PDFs.
