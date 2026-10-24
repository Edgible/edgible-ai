---
title: Private in your gateway
description: Add your private model to your AI gateway as private and private-smart, with a budget and a spending record like any other model.
prev: your-private-model
next: private-for-your-agent
---

# Private in your gateway

*Chapter 3 of [A private model for your agent](../a-private-model-for-your-agent/). Draft: [tell us how it goes](mailto:stefano@edgible.com?subject=Playbook%20feedback).*

Your [AI gateway](../your-ai-gateway/) already offers models by purpose: `fast`, `smart`, `best`. It also has two private slots, `private` and `private-smart`, that have been waiting for a model. This chapter fills them with the one on `edgible-osx`.

Here the second machine earns its keep. The gateway runs on `edgible-vm`. The model runs on `edgible-osx`. The gateway calls it by its Edgible address, with the key from chapter 2, and Edgible checks that key on the Mac before the request reaches anything.

> **What you need**
>
> - [Chapter 2](../your-private-model/) done: the model downloaded, and the key stored as `ollama`.
> - Your gateway from the [agent playbook](../your-ai-gateway/), still called `ai-gateway`.

## 1. Fill the private slots

In Claude, on your phone or computer, say:

> Add my private model to my AI gateway. Use qwen2.5:7b for private and gpt-oss:20b for private-smart, from the ollama app on edgible-osx.

Claude updates the gateway in place and asks first. It points `private` and `private-smart` at your `ollama` app's address, and gives the gateway the stored `ollama` key **by reference**: the key goes from your Edgible account to the gateway, and is never shown or written into a file. Your other models and keys are untouched, and so are the keys and budgets of the agents that use them.

Only used one model so far? Leave out `private-smart`, and say so.

## 2. Check it answers

> Check my AI gateway answers on private.

It sends one tiny question through the gateway to the model on your Mac, and tells you which model answered, how long it took, and what it cost. The first answer after a quiet spell takes longer, while the Mac loads the model into memory.

Then try the bigger one:

> Check my AI gateway answers on private-smart.

## 3. See what it costs

> What has my AI gateway spent, by model?

`private` and `private-smart` appear in the list beside the cloud models, with their questions and tokens counted. We give them a token price, about a cent for every hundred thousand tokens, so budgets still work on them, and it rounds to nearly nothing in the report. Their real cost is your electricity.

## What's different about private

Two rules, both on purpose:

- **`private` never falls back to a cloud model.** If your Mac is asleep or off, `private` doesn't quietly send your question to DeepSeek. It says it can't answer. A fallback would defeat the point.
- **`private-smart` falls back to `private`,** the smaller model on the same Mac, and nowhere else.

## What you've just done

You've added a model to your gateway that the world never sees:

- **It's one more purpose** in the gateway, picked the same way as `fast` or `smart`, with the same per-agent budgets and spending record.
- **Your agents don't know or care where it runs.** They ask for `private`, and the gateway sends them to your Mac.
- **The key is yours to revoke.** If you ever suspect it, delete that one key in Edgible and make another. Nothing else changes.

<details>
<summary>Prefer to do it by hand?</summary>

What Claude does. The gateway is the [litellm card](https://github.com/edgible-org/cards/tree/main/litellm); its README describes both private models and the key.

1. In the gateway's `card.env`, set `LITELLM_PRIVATE_MODEL=ollama/qwen2.5:7b`, `LITELLM_PRIVATE_SMART_MODEL=ollama/gpt-oss:20b`, and `LITELLM_PRIVATE_URL` to your `ollama` app's address, such as `https://ollama.<you>.edgible.app`.
2. Give it the key as `OLLAMA_API_KEY`, from the stored `ollama` secret. The gateway sends it as `Authorization: Bearer <key>`.
3. Restart the gateway, and send a test message to `private` from its admin page.

</details>
