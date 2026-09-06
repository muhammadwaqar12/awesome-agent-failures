# Contributing

One failure mode per pull request. That's the only hard rule.

## What makes a good entry

A good entry is something a reader can **verify for themselves**. The bar is not "this happened to me" — it's "here is how you can make it happen."

Concretely:

- **The symptom is what you observe, not what you infer.** "Accuracy drops after turn 30" is a symptom. "The model gets confused" is not.
- **The cause explains the mechanism.** Why does this happen, structurally? If the answer is "the model is unreliable," the entry isn't ready.
- **The reproduction fits in a terminal, or close to it.** A paragraph someone can follow in ten minutes beats a repo they have to clone. Deterministic is better than probabilistic; if it's probabilistic, say what rate you observed.
- **The mitigation is a change you can make**, not a disposition. "Add a hop counter to the handoff payload and fail at a threshold" is a mitigation. "Prompt it better" is not, and will be sent back.

## What doesn't belong

- Bugs in a specific framework version. Those belong in that framework's issue tracker. This catalog is for failure modes that survive a framework migration.
- Vendor comparisons or benchmarks. There are better repos for that.
- Anything you can't reproduce. If you're confident it's real but can't yet reproduce it, open an issue instead — someone may be able to.
- Confidential material. If you saw this at work, describe the mechanism, never the system. Every entry here should be reconstructable from public knowledge.

## Entry template

Copy this, fill it in, add it to the right section, and keep the ID sequential within its prefix.

```markdown
### PREFIX-NN · Short name

**Symptom** — What you observe. One or two sentences, concrete.

**Cause** — The mechanism. Why this happens rather than what happens.

**Reproduce** — How to trigger it deliberately. Be specific about setup.

**Mitigate** — What actually fixes or contains it. Prefer structural fixes over prompt changes.
```

Prefixes in use: `CTX` (context & memory), `TOOL` (tool use & orchestration), `RAG` (retrieval & grounding), `COST` (cost & runaway behavior), `EVAL` (determinism & evaluation), `OPS` (operations).

Proposing a new category is welcome — open an issue first so we can agree on the prefix before you write entries against it.

## Corrections

If a mitigation here doesn't hold in your environment, that's a real contribution. Open an issue describing what you tried and what happened. Entries that turn out to be wrong get corrected or removed, with the correction credited.

## Style

- Second person, present tense, plain words.
- No hedging adverbs. If something is uncertain, say what's uncertain.
- Numbers where you have them; nothing where you don't. Made-up percentages are worse than no percentages.
- Keep entries under ~200 words. If it needs more, it's probably two entries.

## Review

Content PRs are reviewed within a day or two. If yours has been sitting longer than that, ping the thread — it means it got lost, not that it was rejected.
