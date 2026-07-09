# DeepTutor Multi-Agent Reference

This page records what GitLearnOS should borrow from DeepTutor's multi-agent pattern.

Reference repository and paper:

```text
https://github.com/HKUDS/DeepTutor
https://arxiv.org/abs/2604.26962
```

This is an external design reference, not the product identity of GitLearnOS. GitLearnOS still comes from the original `zhongkao` learning repository pattern and keeps GitHub / local git as the inspectable learning state layer.

## What the paper actually says

DeepTutor separates two layers:

```text
personalized agentic tutoring
→ validated core pipeline

proactive autonomous companionship / TutorBot
→ deployment extension across channels
```

Do not collapse these into one vague "many agents" story.

The paper's core tutoring loop is:

```text
current learner profile + relevant traces
→ task dispatch
→ problem-solving path or question-generation path
→ build trace
→ update memory / learner profile
```

### Problem-solving path

The paper describes three sequential stages:

```text
① Personalized Investigation
→ decompose the question, gather source and learner-state evidence, make a plan

② Step-by-Step Solving
→ execute sub-goals with tool use, observation, compression, and replanning

③ Evidence-Based Writing
→ produce the final explanation with citations and learner-calibrated depth/tone
```

### Question-generation path

The paper describes two stages:

```text
④ Idea Generation
→ generate candidate practice ideas from source context and diagnosed gaps
→ filter and rank ideas

⑤ Critic-Guided Generation
→ create question-answer-explanation triples
→ validate correctness, alignment, and computational results when needed
```

### Memory update path

The paper updates the learner profile through three memory dimensions:

```text
Session History
→ what was covered, difficulty, outcome, performance trend

Weakness Diagnosis
→ active/resolved knowledge gaps, recurring confusion, error evidence

Self-Reflection
→ what tutoring strategy worked or failed, pacing/tone/scaffolding notes
```

### Student-side evaluation insight

One of the most interesting ideas is the student-side design.

The paper describes TutorBench as a student-centric benchmark with source-grounded learner profiles and a first-person interactive protocol. In GitLearnOS terms, this means the system should not only model the tutor side. It should also model the learner side:

```text
learner profile
→ first-person learner request
→ expected knowledge gaps
→ observed response / answer attempt
→ diagnosis
→ profile update
```

This can be treated as a lightweight **Student Proxy** or **Learner Simulator** role in heavier OpenHanako setups. Its job is not to impersonate the real user in production. Its job is to test whether a generated explanation, quiz, or review set would expose the expected gap from the learner's perspective.

### TutorBot path

The paper's proactive agent loop has three broad phases:

```text
context assembly
→ persona / soul, memory, skills, conversation history

ReAct tool-calling loop
→ call LLM, execute tools, append observations until final response or budget exhaustion

persist and consolidate
→ append turn, compress old messages, update long-term profile and session log
```

## What to borrow

DeepTutor's useful pattern is not "create many agents and let them all write state".

The useful pattern is:

```text
main tutor loop
→ consult or dispatch a focused agent only when needed
→ stream or record the agent's work
→ return to the main loop
→ main loop answers in its own voice
→ durable state is written in one controlled place
```

DeepTutor's README describes the default Chat surface as the place where work begins: it can call tools, ground itself in knowledge bases, read attachments, write notebook records, and consult subagents from one turn. Contextual tools such as `rag`, `read_source`, `read_memory`, `write_memory`, `read_skill`, `load_tools`, `exec`, `ask_user`, `write_note`, `github`, and `consult_subagent` mount only when the turn has the right context.

DeepTutor's `consult_subagent` tool is a useful boundary model. The model only supplies a focused `question`; server-side runtime injects the backend, working directory, config, budget, and session state. The consulted agent streams its native run, returns a final answer, and the main model must stop consulting when the budget is exhausted.

DeepTutor's subagent capability also says the consulted agent session can persist across consults, while the main model should answer the user in its own voice rather than impersonating the subagent.

## GitLearnOS adaptation for OpenHanako

For GitLearnOS, OpenHanako multi-agent should use a **controlled pipeline + consultation pattern**, not uncontrolled parallel writing.

### Minimal default

Use this for normal learners:

```text
GitLearnOS Maintainer
→ main tutor loop
→ owns dashboard, learner-profile.md, indexes, handoff notes, and final writes

Source & Model Extractor
→ consulted when source material, mistakes, papers, screenshots, or local excerpts need extraction
→ proposes source records, reusable models, and knowledge gaps

Practice & Review Coach
→ consulted when review sets, quizzes, spaced repetition, or next actions are needed
→ proposes practice and review updates

Validator / Critic
→ optional reviewer
→ checks unsupported claims, stale gaps, weak questions, answer correctness, and learner-profile drift
```

### DeepTutor-inspired expanded pipeline

Use this only when the user wants a heavier OpenHanako setup:

```text
Maintainer / Orchestrator
→ main loop, state boundary, final response, final write

Personalized Investigator
→ maps a user task to source records, current gaps, learner profile, and a plan

Step Solver / Model Extractor
→ executes the plan, extracts reusable models, records observations

Evidence Writer
→ turns the result into a learner-facing explanation or repository note

Practice Idea Agent
→ proposes practice ideas from active gaps and source context

Question Generator
→ creates question-answer-explanation triples

Student Proxy / Learner Simulator
→ tests whether a generated explanation or question exposes the expected gap from the learner's perspective
→ never replaces the real learner's answer in production

Validator / Critic
→ independently checks correctness, source grounding, fit, and difficulty

Memory Updaters
→ Session History, Weakness Diagnosis, and Self-Reflection updates
```

The expanded pipeline should be treated as a configuration option, not as the default GitLearnOS requirement.

## Mapping to GitLearnOS files

```text
Personalized Investigation
→ sources/source-index.md
→ learner-profile.md
→ knowledge-gaps/gap-index.md
→ goals/main-goal.md

Step-by-Step Solving / Model Extraction
→ models/
→ sources/
→ knowledge-gaps/

Evidence-Based Writing
→ dashboard.md
→ reviews/
→ model cards
→ learner-facing explanation notes

Idea Generation
→ reviews/review-index.md
→ reviews/due.md
→ practice candidates

Student Proxy / Learner Simulator
→ simulated first-person learner attempt
→ expected-gap exposure check
→ difficulty and wording feedback
→ never counted as the real user's performance

Critic-Guided Generation / Validation
→ answer keys
→ source links
→ difficulty fit
→ validator notes

Memory Update
→ learner-profile.md
→ agents/handoff-notes/latest.md
→ knowledge-gaps/gap-index.md
→ reviews/review-index.md
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
validate
simulate learner response
```

They should not independently rewrite `learner-profile.md`, `dashboard.md`, `reviews/`, or `knowledge-gaps/` unless the Maintainer explicitly delegates a write and then verifies the result.

## Student Proxy safety rule

A Student Proxy is useful for testing and calibration, not for replacing the real learner.

It may:

```text
simulate how a learner with the current profile might misunderstand a prompt
check whether a question exposes the target gap
flag wording that is too easy, too hard, or too leading
suggest what kind of real learner response should be collected next
```

It must not:

```text
invent real learner performance
mark a knowledge gap as resolved
write final grades or mastery status
pretend the user answered a question
```

Only real learner responses or explicit user confirmation can update mastery, resolved gaps, or performance trends.

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
expanded pipeline task: explicit user approval required
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

DeepTutor can inspire the agent pipeline and consultation pattern, but GitLearnOS state remains file-based and inspectable.

## What not to copy

Do not copy DeepTutor's full platform scope into GitLearnOS docs.

Do not require:

```text
full DeepTutor install
multi-user deployment
Knowledge Center / RAG engine stack
DeepTutor trace forest implementation
DeepTutor three-layer memory system
partner workspace system
DeepTutor CLI
DeepTutor web app
```

Those are DeepTutor platform features. GitLearnOS should borrow only the controlled multi-agent pipeline shape, the consult-budget boundary, the student-side evaluation insight, and the learner-state feedback loop.
