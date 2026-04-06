# kevin-mode

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Stars](https://img.shields.io/github/stars/ajmalhassan/kevin-mode)
[![Install with skills CLI](https://img.shields.io/badge/install-npx%20skills%20add-brightgreen)](https://skills.sh)

**Why waste time say lot word when few word do trick?**

I kept watching Claude narrate every action like a sports commentator. "I'll read the file now." "Let me check the configuration." "Here's a summary of what I did." That's tokens I'm paying for and attention I'm losing.

So I turned Kevin Malone's philosophy into a **Claude Code skill** that cuts ~35-45% of output tokens — dropping filler prose and low-value narration while keeping the explanations that actually matter.

## Quick Install (recommended)

```bash
npx skills add ajmalhassan/kevin-mode
```

<details>
<summary>Other install methods</summary>

Clone into skills directory:

```bash
git clone https://github.com/ajmalhassan/kevin-mode.git ~/.claude/skills/kevin-mode
```

Or copy just the skill file:

```bash
mkdir -p ~/.claude/skills/kevin-mode
cp SKILL.md ~/.claude/skills/kevin-mode/
```

</details>

## What It Does

| What gets cut | What stays |
|---------------|------------|
| Articles, filler pronouns, transition words | Non-obvious *why* explanations |
| "Let me X" announcements | Genuine questions |
| Trailing summaries | Risk/warning flags |
| Restating what you just said | All code output |
| Status updates for obvious actions | Commits, PRs, docs (others read those) |

## Before & After

**Explaining a change:**

> Normal: "I'll read the configuration file to understand how the routes are set up. I can see the middleware chain uses express.Router(). I'll add the new endpoint after the existing auth routes. The POST handler needs to come before the catch-all route so it doesn't get swallowed."
>
> Kevin: "POST handler before catch-all — catch-all swallows it otherwise."

**Asking a question:**

> Normal: "We could add validation in the middleware layer or directly in the handler function. Middleware catches invalid requests earlier. Which approach would you prefer?"
>
> Kevin: "Validation — middleware or handler? Middleware catches earlier."

**Completing a task:**

> Normal: "I've finished implementing the changes. I updated the parser, added validation, and updated the tests. All 12 pass. Let me know if you'd like adjustments."
>
> Kevin: "Done. Parser, validation, tests. 12 pass."

## Usage

Invoke directly:

```
/kevin-mode
```

## Projected Token Savings

| Output type | Reduction |
|-------------|-----------|
| Prose tokens | ~60-70% |
| Code tokens | ~0% (unchanged) |
| Tool calls | ~5-10% (fewer confirmation rounds) |
| **Net output** | **~35-45%** |

## Why Not Just Use System Prompts?

You could paste "be terse" into your CLAUDE.md. But it drifts — Claude gradually returns to its verbose defaults mid-session. A skill is loaded fresh on invocation and provides concrete examples that calibrate the style precisely.

## License

MIT
