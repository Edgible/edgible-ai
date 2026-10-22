---
title: Your agent
description: Your own AI agent, OpenClaw, on your machine, using your AI gateway with its own key and budget, behind your Edgible sign-in.
---

# Your agent

*Chapter 4 of [Your own AI agent, from anywhere](../your-own-ai-agent/). Draft: being tested now.*

Now the agent itself. It's **OpenClaw**, a popular open-source AI agent: it chats, remembers, researches, and uses tools on your behalf. Yours comes with Edgible's tools and skill built in, so it can also look after your apps, asking you first before it changes anything.

It runs on your machine, uses your AI gateway with **its own key and its own budget**, and only you can open it.

> **What you need**
>
> - [Chapters 1 to 3](../your-own-ai-agent/) done: Edgible running, Claude connected, and your AI gateway.
> - **4 GB of memory** free on the machine, on top of the gateway.

## 1. Ask Claude to set it up

In Claude, say:

> Set up my own AI agent on my edgible-vm. It should use my AI gateway, with a budget of five dollars a month.

Claude does three things, and asks before each:

- **Makes the agent's own gateway key,** with its five-dollar budget. The key goes straight into your Edgible account; neither you nor the agent's settings ever show it.
- **Sets the agent up** on your machine, with your gateway as its only way to reach an AI model.
- **Locks it to you:** the agent's address opens only after you sign in with your Edgible account.

At the end, it gives you the agent's address.

## 2. Meet your agent

Open the address, and sign in with Edgible. You're in OpenClaw: a chat, with your agent on the other side. Say hello:

> What can you do for me?

Its first answers come from **fast**, your gateway's everyday model. The menu by the message box lets you pick another, such as **smart** for harder questions, or **best** when it really matters.

## 3. Let it look after your apps

Your agent has Edgible's tools, but they need your permission once. Ask it:

> Sign in to Edgible.

It shows a link and a short code, as in chapter 1: open the link, check the code, and approve. Then try:

> What's running on my Edgible?

## 4. Ask what it has spent

> What have you spent so far?

It answers with its own spending against its budget, and only its own. It can't see what your other agents spend: that view is yours, in Claude.

## What you've just done

You have your own AI agent, and it's well brought up:

- **It's yours.** It runs on your machine. Its memory, your files and your conversations stay there.
- **Only you can open it,** behind your Edgible sign-in. No password of its own to leak, and no ports open.
- **It can't run up a bill.** It has its own key and budget on your gateway. At its limit it stops; it never sees your provider keys, and it can't touch other agents' budgets.
- **It knows its own spending,** and you see everyone's.
- **It asks before it acts** on your apps, every time.

Most people trying agents give one a provider key and hope. Yours has guardrails from the first message.

Next: [Run it from your phone](../your-own-ai-agent/).

<details>
<summary>Prefer to do it by hand?</summary>

The agent is the [edgible-agent card](https://github.com/edgible-org/cards/tree/main/edgible-agent), in its shared-gateway mode: its README has every step.

</details>
