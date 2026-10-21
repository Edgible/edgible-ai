---
title: Get Edgible running
description: Put Edgible on a computer that stays on, with your AI assistant doing the technical work. The first chapter of every playbook.
---

# Get Edgible running

This is the first chapter of every playbook. By the end, a computer of yours runs Edgible, ready for apps that you and the people you choose can reach from anywhere.

Your AI assistant does the technical work. You tell it what you want, approve a couple of things in your browser, and answer a few questions. It takes about fifteen minutes.

Done this already? Skip to your playbook.

> **What you need**
>
> - **A computer that stays on:** a Mac, or a PC or small server running Linux, such as Ubuntu. A spare one is ideal. On Windows, Edgible runs in a Linux virtual machine. No suitable computer? A chapter on getting one, such as a small cloud server for a few dollars a month, is coming soon.
> - **Claude Code,** in the Claude desktop app, on that computer. It comes with Claude's paid plans. Other assistants that read skills, such as Codex, work too.
> - **An Edgible account.** It's free during the public beta, and your AI will help you make one.

## 1. Open Claude Code

In the Claude desktop app, switch to **Code**, and choose a folder for it to work in: a new, empty one is fine.

Claude Code is the part of Claude that can work on your computer. It always asks before it changes anything.

## 2. Give it the Edgible skill

The skill is Edgible's recipe book for AI assistants: how to set Edgible up, our tested app recipes, and how to look after them. Say:

> Install the Edgible skill from github.com/edgible-org/card-kit

## 3. Ask it to set up Edgible

> Set up Edgible on this computer so I can run my own apps.

It checks your computer first, then takes you through the rest. Along the way:

- **Your account.** If you don't have one yet, it sends you to [edgible.com](https://www.edgible.com) to sign up and create an organisation, the name your apps live under. It never asks for your password.
- **The Edgible software.** It says what it will install, and asks before it does. Your computer may ask for its own password.
- **Signing in.** It shows you a link and a short code. Open the link, check the code matches, and approve. That's how this computer gets permission to act for your account.
- **A name for this computer,** such as `minipc` or `office-mac`. It's how you'll recognise it later.
- **Whether it should stay on.** Say yes for anything other people rely on: Edgible then starts by itself whenever the computer starts.

## 4. Check it worked

> Is Edgible running on this computer?

It should say the computer is **online**. You can also see it, by the name you gave it, in your [Edgible console](https://app.prod.edgible.com/).

## What's next

Edgible is running, and your AI knows how to use it. Go back to your playbook, or simply say what you need:

> It costs us $40 a month to host our small website. Is there a better way?

If something goes wrong, tell your AI what you see. The skill knows Edgible's error messages and their fixes.

<details>
<summary>Prefer to do it by hand?</summary>

These are the commands your AI runs, on macOS or Linux. You need `curl`, `unzip` and Node.js 20 or later.

```bash
# Install the Edgible command-line tool
curl -fsSL https://get.edgible.com/install.sh | bash
export PATH="$HOME/.local/bin:$PATH"

# Sign in: open the link it prints, and approve
edgible auth login --no-browser

# Make this computer a device that starts by itself (choose your own name)
sudo ln -sfn "$HOME/.local/bin/edgible" /usr/local/bin/edgible
sudo edgible install --device-name minipc --yes

# Check
edgible agent status
```

The full walk-through is Edgible's [Start here](https://guides.edgible.com/) guide.

</details>
