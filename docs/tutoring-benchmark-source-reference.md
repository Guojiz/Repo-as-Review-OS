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
cross-channel source records
+ automatic organization
+ evidence-linked learner profile and gaps
+ targeted question and external-handoff skills
+ optional tutoring and observable scoring
+ learner policy and Git history
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
| Does practice expose a real gap? | question set links goal, gap, model, source, and prior result |
| Can external learning enter the loop? | teacher handoffs and feedback reconcile into canonical state |
| Does the loop close? | feedback or learner result changes resolution, evidence, and next action |
| Can the learner inspect and control it? | policy, Markdown state, receipts, and Git history remain editable |

This document records design provenance; it does not bundle or redistribute DeepTutor source material or benchmark PDFs.
