# Playbooks

The playbooks at www.edgible.ai/playbooks. Each chapter is one Markdown file here, built into a page in the site's look (`npm run build`), with the Markdown published beside it for AI assistants.

A chapter starts with its title and a one-line description:

```markdown
---
title: Get Edgible running
description: Put Edgible on a machine that stays on, with your AI assistant doing the work.
---
```

How a chapter reads:

- **Prompts and links, not commands.** The reader tells their AI what they want; any command goes under a "Prefer to do it by hand?" section at the end, in a `<details>` block.
- **Keys through the key link,** never pasted into a chat or a command.
- **Plain words** for people who are comfortable with technology but not technical.
- **Tested.** Every prompt in a chapter has been run, and the AI regression checks that assistants follow it.

`index.md` is the list of playbooks; this README is not published.
