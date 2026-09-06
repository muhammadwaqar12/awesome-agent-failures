# Contributing

One failure mode per pull request. That is the only hard rule.

## What makes a good entry

A good entry is something a reader can verify without taking my word for it. The bar is not "this happened to me." It is "here is how you can make it happen."

Concretely:

- **The symptom is what you observe, not what you infer.** "Accuracy drops after turn 30" is a symptom. "The model gets confused" is not.
- **The cause explains a mechanism.** Why does this happen, structurally? If the answer comes out as "models are unreliable," the entry is not ready yet.
- **The reproduction fits in a terminal, or close to it.** A paragraph someone can follow in ten minutes beats a repo they have to clone. Deterministic beats probabilistic. If it is probabilistic, say what rate you saw.
- **The mitigation is a change someone can make.** "Add a hop counter to the handoff payload and fail at a threshold" is a mitigation. "Prompt it better" is a disposition, and it will get sent back.

## What does not belong

- Bugs in a specific framework version. Those belong in that framework's issue tracker. This catalog is for failures that survive a framework migration.
- Vendor comparisons and benchmarks. There are better repos for that.
- Anything you cannot reproduce. If you are confident it is real but cannot reproduce it yet, open an issue instead. Someone else may be able to.
- Confidential material. If you saw this at work, describe the mechanism and never the system. Every entry here should be reconstructable from public knowledge by someone who has never seen your codebase.

## Entry template

Copy this, fill it in, drop it in the right section, and keep the ID sequential within its prefix.

```markdown
### PREFIX-NN: Short name

**Symptom:** What you observe. One or two sentences, concrete.

**Cause:** The mechanism. Why this happens rather than what happens.

**Reproduce:** How to trigger it deliberately. Be specific about setup.

**Mitigate:** What actually fixes or contains it. Structural fixes beat prompt changes.
```

Prefixes in use: `CTX` for context and memory, `TOOL` for tool use and orchestration, `RAG` for retrieval and grounding, `COST` for cost and runaway behavior, `EVAL` for determinism and evaluation, `OPS` for operations.

New categories are welcome. Open an issue first so we can settle on the prefix before you write entries against it.

## Corrections

If a mitigation here does not hold in your environment, that is a real contribution. Open an issue describing what you tried and what happened instead. Entries that turn out to be wrong get corrected or removed, and the correction gets credited.

## Style

- Second person, present tense, plain words.
- No hedging adverbs. If something is uncertain, say what is uncertain.
- Numbers where you have them and nothing where you do not. An invented percentage is worse than no percentage.
- Keep entries under roughly 200 words. If it needs more, it is probably two entries.

## Review

Content pull requests get reviewed within a day or two. If yours has been sitting longer than that, ping the thread. It means it got lost, not that it was rejected.
