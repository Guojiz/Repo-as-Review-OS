# Local Runtime Note

Repo as Review OS can run across three layers, but the layers are not equal.

```text
GitHub repository
→ the durable learning state: structure, indexes, models, reviews, dashboard, agent rules, handoff notes, and history

ChatGPT Project or another AI project space
→ fixed reference materials, project instructions, and current conversation context

Local folders
→ original learning files and large subject folders kept outside the repository
```

## ChatGPT Project boundary

A ChatGPT Project is useful, but it should not be treated as the whole learning OS.

Use it mainly for:

- fixed textbooks or selected excerpts;
- stable project instructions;
- a small number of reference files;
- current conversations around those materials.

Do not rely on it as the main place for:

- long-term dynamic notes;
- large source libraries;
- many changing files;
- review history;
- generated practice archives;
- learner profile updates;
- cross-agent handoff state;
- Git-style version history.

In plain terms:

```text
ChatGPT Project = fixed material shelf and conversation layer
GitHub repository = durable learning state and writeback layer
Local folders = protected source and working-file layer
```

The project space can help ChatGPT read a textbook or stable notes, but the repository should remain the source of truth for the learning system.

## ChatGPT memory and GitHub sync

ChatGPT memory is useful for stable preferences and a compact learner summary.

GitHub should remain the source of truth for concrete learning state:

```text
ChatGPT memory
→ stable preferences, explanation style, broad learner summary

GitHub repository
→ goals, source records, models, reviews, generated practice, dashboard, handoff notes, and version history
```

They should be kept aligned, but they should not be treated as the same thing.

Use this rule:

```text
If GitHub and memory conflict, trust GitHub first.
Then update or correct the memory summary if needed.
```

A useful maintenance step is to compare the current ChatGPT memory or project instructions with the repository state:

- if memory contains a stable preference missing from the repository, record it in the appropriate repo note;
- if GitHub contains a newer learner-state summary, update the memory or project instructions;
- if either side is uncertain, ask the user before treating it as permanent.

## For ChatGPT Plus users

A user does not always need Codex for daily learning.

A practical setup can be:

```text
ChatGPT Project
+ selected fixed materials
+ ChatGPT memory for stable preferences
+ Repo as Review OS instructions
+ GitHub repository
+ local subject folders
```

ChatGPT can handle many daily tasks when the GitHub connector or another safe writeback path is available.

Without repository writeback, ChatGPT Project should be treated as a reading and conversation space, not as proof that the learning repository has been updated.

Codex or another coding agent is useful for larger repository operations, but it is not required for every review session.

## Visual and math work

Do not add a separate desktop agent just for visuals by default.

If the current ChatGPT environment can create diagrams, images, tables, code, or interactive explanations, use those built-in abilities first.

For math visualization, the AI may create:

- a Desmos-ready expression list;
- a small HTML demo;
- Python code;
- a diagram or step-by-step visual explanation.

Only write the artifact back to GitHub when the current chat actually has repository write access.

## Local runtime is not the same as GitHub runtime

A local AI workspace can reproduce many parts of Repo as Review OS:

- files and folders;
- local read and write;
- a local dashboard;
- local notes;
- local review records;
- optional local git history.

But a local workspace is not identical to a GitHub repository.

The user may not be able to open the file tree in a browser, inspect rendered Markdown, check remote commit history, use GitHub Issues, or collaborate through forks and pull requests.

If the AI only has local file access, it must say so clearly.

It should not claim that GitHub setup, GitHub write access, push, Issues, or remote repository updates have happened unless it has actually verified those permissions and actions.

Use this distinction:

```text
Local reproduction
→ useful for testing the method locally
→ may read and write local files
→ may use local git if configured
→ does not automatically mean GitHub access

GitHub-backed Review OS
→ user can open the repository directly
→ user can inspect history and files
→ AI changes can be verified in GitHub
→ better for long-term use and handoff
```

## Suggested local folders

```text
Learning-OS-Local/
├── Chinese/
├── Math/
├── English/
├── Physics/
├── History/
└── _shared/
```

Each subject folder may contain the user's own working files, notes, drafts, screenshots, PDFs, and exports.

Only selected excerpts, source records, summaries, or links need to be copied into GitHub.

## Repository link to local folders

If an important source stays outside GitHub, create a source record in GitHub:

```text
status: local-only-source
subject: Math
where it lives: local Math folder
what AI can see: selected excerpt only
```

The AI must not pretend it has read a local-only source.

It should ask for the relevant excerpt or mark the source as incomplete.

## Positioning

GitHub is the operating layer.

ChatGPT memory is the compact preference and learner-summary layer.

The AI project is the fixed-material and conversation layer.

Local folders are the protected working layer.

Do not collapse all layers into one place.