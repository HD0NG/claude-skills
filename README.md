# claude-skills

Personal library of Claude skills for research workflows, writing, coding, and productivity.

---

## What's a skill?

A skill is a Markdown instruction file (`SKILL.md`) that tells Claude how to handle a specific type of task. When installed, Claude reads the skill's description and decides when to use it automatically — no re-prompting required.

Each skill lives in its own folder:

```
skill-name/
├── SKILL.md          # Core instructions and trigger description
├── references/       # Optional: domain docs, guides, cheat sheets
└── assets/           # Optional: templates, scripts, other files
```

Packaged skills are distributed as `.skill` files (a zip archive of the folder).

---

## Structure

```
claude-skills/
├── README.md
├── research/          # LiDAR pipelines, data processing, scientific workflows
├── writing/           # Email drafts, academic writing, documentation
├── coding/            # Code review, debugging patterns, language-specific helpers
└── productivity/      # General task helpers, formatting, planning
```

---

## Using a skill

1. Open [Claude.ai](https://claude.ai) → Settings → Skills
2. Upload the `.skill` file
3. Start a conversation — Claude will pick up the skill automatically when relevant

---

## Building a skill

The fastest way is to ask Claude directly:

> "Help me build a skill for [workflow]."

Claude will interview you, draft the `SKILL.md`, run test cases, and package the result. See [Anthropic's skill-creator documentation](https://docs.claude.ai) for the full process.

### Key principles

- **Description = trigger.** The `description` field in the YAML frontmatter is what tells Claude when to use the skill. Write it to match the prompts you actually use.
- **Keep `SKILL.md` under ~500 lines.** Move heavy reference material into `references/` and link to it from the main file.
- **Test before committing.** A skill that misfires (triggers when it shouldn't, or doesn't trigger when it should) is worse than no skill.

---

## Skills in this repo

| Skill | Category | Description |
|-------|----------|-------------|
| *(none yet)* | — | — |

---

## Notes

- Skills are personal and may contain domain-specific context (project names, preferred formats, writing style). Review before sharing.
- Claude has no memory of skill contents between sessions — the skill file is re-read each time it's triggered.
- Tested against Claude Sonnet unless noted otherwise.
