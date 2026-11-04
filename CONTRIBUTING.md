# Contributing

This repository holds a **skill**: a folder of instructions an agent loads when a task matches. There is no runtime, no build, and no application code. That shapes what a useful contribution is.

Short version:

> Corrections are welcome as pull requests. Changes to the method are welcome after an issue.

---

## Two lanes

### Fast lane — open a pull request directly

- Typo, broken link, wrong command, inaccurate statement.
- A **complete** translation of `SKILL.md` plus the eight references.
- A clearer sentence that says the same thing.
- A bug in `scripts/validate-skill.sh`, with the case that reproduces it.

### Slow lane — open an issue first

- Changing, adding, or removing one of the **eight principles**.
- Changing the **gate vocabulary** — `PASS`, `FAILED`, `BLOCKED`, `NOT RUN`.
- Adding or merging a **phase** (A–G).
- Changing the mandatory fields of the `BP-00X` schema.
- Adding a reference file, or a new section to `SKILL.md`.
- Anything that makes the skill longer without making it more precise.

An issue needs three things, and will be closed without them:

1. **A real case** where the skill gave the wrong instruction, or none.
2. **Why the existing text does not cover it** — quote the line.
3. **What gets worse** if we add it: length, ambiguity, one more thing to remember.

"I prefer it this way" is not a case. The value of this skill is that it is short and decided.

---

## Invariants

Not up for discussion inside a pull request. Breaking one is a rejection, not a review comment.

| Invariant | Why |
|---|---|
| `name` in the frontmatter is **identical** to the directory name | hosts resolve skills by folder; a mismatch silently fails to load |
| Exactly **four gate states** | adding a fifth ("partial", "mostly done") destroys the distinction the skill exists to make |
| `NOT RUN` is never reported as `PASS` | it is the failure this skill exists to prevent |
| The **seven phases** stay A–G | the references and the translations point to them by letter |
| Translations keep code blocks, paths, phase names, and the `BP-00X` schema **identical** | otherwise the versions drift and cannot be compared |
| **No absolute paths** in any `.md` | it must work on someone else's machine |
| **No secrets**, ever | public repository |
| The **Matt Pocock attribution** stays in `README.md` | the method is inspired by published work; the credit is not ours to drop |

---

## Definition of done

Both must be true:

```bash
bash scripts/validate-skill.sh      # must print PASS and exit 0
```

- `CHANGELOG.md` has an entry under `[Unreleased]`, one line describing the change.

The validator checks what breaks silently: name/directory match, references that exist and are not orphaned, absolute paths, the four gate states being documented, `SKILL.md` length, obvious secrets, and the changelog section. It needs only bash and coreutils.

---

## Writing style

The skill is read by an agent under a token budget, and by a human deciding whether to trust it.

- **Direct voice.** "Never advance without a gate", not "it may be advisable to consider".
- **Italian for the skill body** (the canonical language), **English for the README** and for anything a non-Italian reader needs.
- **No hype.** No "supercharge", "10x", "game-changing".
- **Short sentences.** One rule, one idea.
- **No emoji** in `SKILL.md` or in the references.
- **Numbers over adjectives.** "≤ 200 lines" beats "reasonably short".
- **Name the failure.** A rule without the failure it prevents is decoration.

---

## Commits

- One logical change per commit.
- Imperative mood: `Clarify baseline tests in Phase E`, not `Fixed stuff`.
- Reference the issue when one exists: `Tighten gate rule (#4)`.

A rule change mixed with cosmetic edits will be asked to split.

---

## What gets rejected

- Rewrites that change wording without changing meaning.
- A fifth gate state, or a state that means "almost".
- Tools or third-party skills added as if they were bundled, without verification.
- Commands with flags nobody executed.
- Growth in `SKILL.md` instead of a reference file — it is read on every matching task.
- Anything that requires a paid service to follow the instructions.

---

## Licensing

Contributions are accepted under the **MIT license** of this repository (inbound = outbound). No CLA, no copyright assignment. By opening a pull request you confirm you wrote the content or that it may be redistributed under MIT.

---

## Local workflow

Clone into a folder named `phased-build-orchestrator`: the validator compares the frontmatter `name` with the directory name, because that is how hosts resolve a skill. Cloning into `my-folder` fails that check — correctly, but it is not a defect in the repository.

```bash
git clone https://github.com/nemesis1978/phased-build-orchestrator.git
cd phased-build-orchestrator
bash scripts/validate-skill.sh      # baseline: PASS

# make your change
bash scripts/validate-skill.sh      # must still PASS

git add -A
git commit -m "Describe the change in the imperative"
```

To try the skill in an agent before opening a pull request, copy the directory into that agent's skills path and restart the session.

If your change alters behaviour rather than wording, say in the pull request **which prompt you ran and what the agent did differently** — especially whether it stopped at a gate it used to skip. That is the only evidence that matters for an instruction file.
