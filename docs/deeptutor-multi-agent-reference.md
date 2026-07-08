# DeepTutor Multi-Agent Reference

This page records what GitLearnOS should borrow from DeepTutor's multi-agent pattern.

Reference repository:

```text
https://github.com/HKUDS/DeepTutor
```

This is an external design reference, not the product identity of GitLearnOS. GitLearnOS still comes from the original `zhongkao` learning repository pattern and keeps GitHub / local git as the inspectable learning state layer.

## What to borrow

DeepTutor's useful pattern is not "create many agents and let them all write state".

The useful pattern is:

```text
main chat / tutor loop
→ consult a focused subagent when needed
→ stream or record the subagent's work
→ return to the main loop
→ main loop answers in its own voice
→ durable state is written in one controlled place
```

In DeepTutor, the default chat surface can call tools, ground itself in knowledge bases, read attachments, write notebook records, and consult subagents from one turn. Its README describes contextual tools such as `rag`, `read_source`, `read_memory`, `write_memory`, `read_skill`, `load_tools`, `exec`, `ask_user`, `write_note`, `github`, and `consult_subagent` as mounting only when the turn has the right context.

DeepTutor's `consult_subagent` tool is also a useful boundary model. The model only supplies a focused `question`; server-side runtime injects the backend, working directory, config, budget, and session state. The consulted agent streams its native run, returns a final answer, and the main model must stop consulting when the budget is exhausted.

DeepTutor's subagent capability says the chat loop runs on a limited consult budget, the consulted agent session can persist across consults, and the main model should answer the user in its own voice rather than impersonating the subagent.

## GitLearnOS adaptation

For GitLearnOS, this means OpenHanako multi-agent should use a **consultation pattern**, not uncontrolled parallel writing.

Recommended OpenHanako shape:

```text
GitLearnOS Maintainer
→ main loop
→ owns dashboard, learner-profile.md, indexes, handoff notes, and final writes

Source & Model Extractor
→ consulted when source material, mistakes, papers, screenshots, or local excerpts need extraction
→ proposes source records, reusable models, and knowledge gaps

Practice & Review Coach
→ consulted when review sets, quizzes, spaced repetition, or next actions are needed
→ proposes practice and review updates

Critic
→ optional consulted reviewer
→ audits vague notes, unsupported claims, stale gaps, weak questions, and learner-profile drift
```

## Final writer rule

Only the Maintainer should write durable state by default.

Other agents may:

```text
inspect
propose
extract
summarize
quiz
audit
```

They should not independently rewrite `learner-profile.md`, `dashboard.md`, `reviews/`, or `knowledge-gaps/` unless the Maintainer explicitly delegates a write and then verifies the result.

## Consult budget rule

Borrow DeepTutor's budget idea:

```text
one user request
→ small number of subagent consults
→ stop consulting
→ Maintainer writes or reports final result
```

A good default:

```text
normal task: 0-1 consult
source-heavy task: 1-2 consults
complex repository repair: 2-3 consults
```

More than that usually means the system is drifting and should ask the learner or write a handoff note.

## Self-contained question rule

Every subagent consult should be self-contained:

```text
Task:
Context:
Files or sources allowed:
Output format:
Write permission:
Stop condition:
```

Never assume the subagent can see the full parent conversation unless the runtime explicitly passes that context.

## Voice rule

The final answer belongs to the Maintainer or active main runtime.

Do not answer as the subagent. Do not say "I" from the subagent's point of view. Summarize what the subagent found, then make the final decision in the main runtime's voice.

## State rule

The learning state layer remains:

```text
GitHub target repository
or local git
or local git + Obsidian
```

DeepTutor can inspire the agent consultation shape, but GitLearnOS state remains file-based and inspectable.

## What not to copy

Do not copy DeepTutor's full platform scope into GitLearnOS docs.

Do not require:

```text
full DeepTutor install
multi-user deployment
Knowledge Center / RAG engine stack
three-layer DeepTutor memory
partner workspace system
DeepTutor CLI
DeepTutor web app
```

Those are DeepTutor platform features. GitLearnOS should borrow only the controlled multi-agent consultation pattern.
