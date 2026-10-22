---
title: Your AI gateway
description: Cost guardrails before you run an agent: one place for your AI keys, a budget for every agent, and the spending in real dollars, on your own machine.
---

# Your AI gateway

*Chapter 3 of [Your own AI agent, from anywhere](../your-own-ai-agent/). Draft: being tested now.*

Before you run an agent, put the guardrails in. An AI gateway sits between your agents and the AI providers, and gives you:

- **One place for your keys.** You store each provider's key once. Your agents never see them: each gets its own gateway key instead.
- **A budget per agent.** Each agent can spend only its own budget, say five dollars a month. A runaway agent stops at its limit, not at your credit card's.
- **The real dollars.** What each agent spent, on which model, from your phone.
- **Models by purpose, not by name.** Agents ask for *fast*, *smart* or *best*, and you decide which model each one means, and change it any time.
- **A backup.** When a provider has an outage or a free tier runs out, the next one answers.

The gateway is LiteLLM, the most widely used open-source AI gateway, in a version we've tested.

> **What you need**
>
> - Chapters 1 and 2 done, on a machine with **4 GB of memory** or more.
> - **A DeepSeek account** with a little credit: [platform.deepseek.com](https://platform.deepseek.com), then API keys. Five dollars goes a long way.
> - Optional: **Gemini** as a free backup ([aistudio.google.com/apikey](https://aistudio.google.com/apikey)), **OpenRouter** for open models such as GLM and Kimi, **Anthropic** for Claude Opus when it really matters.

## 1. Set up the gateway

In Claude, say:

> Set up an AI gateway on my edgible-vm, called ai-gateway. I'll use DeepSeek, with Gemini as a backup.

It checks the machine, then asks you one thing: whether to give the gateway an address your apps can call. Say yes. That address answers only apps holding a key the gateway gave them, and each app gets its own key and budget. Your connector keeps the gateway's own master key, so you never handle it.

## 2. Store your keys

If you stored these keys with Edgible before, Claude simply uses them and skips this step. Otherwise, Claude gives you a **key link** for each provider. Open it, paste the key from the provider's page, and save. The key goes straight to your Edgible account, never into the chat. Links work once, for ten minutes, and from your phone too.

You only ever do this once. Every agent you add later uses the same keys, through the gateway.

## 3. Check it answers

> Check my AI gateway answers.

It sends one tiny question through the gateway, and tells you which provider answered, how long it took, and what it cost: a tiny fraction of a cent.

## The models, by purpose

| Ask for | Means, to start with | For |
| --- | --- | --- |
| **fast** | DeepSeek, with Gemini as a backup | Everyday answers |
| **smart** | DeepSeek's reasoning model | Harder questions |
| **open** | GLM, through OpenRouter | Trying strong open models |
| **best** | Claude Opus, capped at five dollars a month | When it really matters |
| **private** | A model on your own machine | Anything that must not leave it |

Change any of them by asking: *"Make smart use Gemini Pro."* A model without a key simply passes to its backup.

## What you've just done

You've put the guardrails in before letting an agent loose, which is exactly the right order:

- **Your keys are in one safe place,** stored once, never written into a chat, a file or an app.
- **Every agent you add gets its own key and budget.** If one misbehaves, it stops at its limit, and you can switch it off without touching the others.
- **You'll see the real dollars,** by agent and by model, whenever you ask.
- **It's yours.** No middleman between your agents and the providers, no markup, and nobody else's dashboard.

Most people running agents have none of this, and find out at the end of the month.

<details>
<summary>Prefer to do it by hand?</summary>

What Claude does, in order. The gateway is the [litellm card](https://github.com/edgible-org/cards/tree/main/litellm); its README has every step, and our regression runs it as written.

1. **Store your provider keys** with Edgible, each from a file holding just the key: `edgible secret set deepseek --from-file key=deepseek.txt`, and the same for `gemini`. Then delete the files.
2. **On the machine, the litellm card.** Pass the keys to it by name, then Check, Start, and publish `litellm` on `org` (the admin page).
3. **Publish its API** as `litellm-api` on `none`, as the README's Share it step shows: it answers only keys the gateway issued.
4. **Check it:** sign in to the admin page as `admin`, with the master key the README's `show` command prints on the machine, and send a test message to `fast`. The admin page is also where you make agents' keys and see spending.

Claude does one more thing you don't need by hand: it gives your connector the gateway's address and master key, so you can ask Claude about spending.

</details>
