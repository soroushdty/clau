# Clau — Prompt Polisher

> A custom GPT for ASU members that turns rough ideas into polished, reusable prompts — with optional version history, structured exports, and diff tracking.

Available to ASU members via the shared ChatGPT workspace. No setup required.

---

## What it does

Clau takes a plain description of what you want a prompt to do and produces a clean, ready-to-use prompt. You refine it through natural conversation until it's right, then download it as a structured Markdown file — or just copy it from chat.

It doesn't execute prompts. It doesn't answer questions. It only produces prompts.

---

## Modes

Clau asks you to choose a mode at the start of every session. **Mode is locked for the session** — start a new chat to switch.

### Basic — stateless

Best for quick one-off prompts. No commands, no history, no complexity.

- Type a description → get a prompt
- Keep replying to refine it
- Say **"help"** (or **"h"**, **"?"**, or any recognizable variant) for guidance
- Say **"new prompt"** to start over
- Say **"download"** to get a plain `.md` file

That's everything Basic mode does.

### Advanced — stateful

Best for prompts you'll iterate on seriously, reuse, or share. Every iteration is a saved, named version you can reference, diff, and export with full metadata.

| Command | Alias | What it does |
|---|---|---|
| `/help` | `/h`, `?` | Show the full command reference |
| `/versions` | `/v` | List all versions inline |
| `/diff` | `/d` | Show full version changelog |
| `/reset` | `/r` | Start a new version chain (session memory preserved) |
| `/contact` | `/c` | Bug reports and feedback info |

No command = modify the current prompt.

Commands are case-insensitive. Shortened or misspelled forms are accepted if intent is clear.

---

## Version references (Advanced)

You can reference any earlier version using natural language. All of the following are equivalent:

```
Version 3 / V3 / v3 / @V3 / #V3 / @3
```

Examples:
```
Use the constraints from Version 2.
Restore the examples from V4.
Merge Version 1 and Version 5.
```

---

## Downloads (Advanced)

Prompt Polisher outputs to chat by default. Ask explicitly to get a file:

```
download this
give me the markdown
export v3 as a spec
```

### Prompt file — `[title]-v[N].md`
Plain prose prompt with YAML frontmatter: title, version, creation date, target model, change summary.

### Spec file — `[title]-requirements-v[N].md`
Requirements format: flat `REQ-001`, `REQ-002`... sequence, atomic testable statements, grouped into titled sections. Useful for tooling specs, agent instructions, or structured feature definitions.

### Diff file — `[title]-diff.md`
Full version table: version number, timestamp, change summary, status.

---

## Basic vs Advanced — which should I use?

| | Basic | Advanced |
|---|---|---|
| Generate + refine | ✓ | ✓ |
| Download current state | ✓ | ✓ |
| Named version history | — | ✓ |
| Reference earlier versions | — | ✓ |
| `/diff` changelog | — | ✓ |
| Metadata in downloaded file | — | ✓ |
| Spec format export | — | ✓ |

If you're not sure, start with **Basic**. You can always open a new chat in Advanced mode.

---

## Feedback and bugs

Read `/help` first — most questions are answered there.

- **Technical:** open an issue on this repo
- **Everything else:** [www.soroushdianaty.com](https://www.soroushdianaty.com)

Please include the version number and a clear description of the issue.

---

## For ASU workspace admins

The GPT instructions live in [`prompt-polisher-instructions.md`](./prompt-polisher-instructions.md). Paste the contents of that file into the ChatGPT custom GPT "Instructions" field verbatim. The only field to update before deploying is `[GITHUB_URL]` in the contact block — replace it with the URL of this repo (`github.com/[your-handle]/clau`).

The instructions are under 8,000 characters and have been tested against the ChatGPT custom GPT character limit.

---

*Built by [Soroush Dianaty](https://www.soroushdianaty.com) · ASU College of Health Solutions*
