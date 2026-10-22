---
title: Take it all down
description: Remove what the AI agent playbook set up, cleanly, keeping your data or deleting it, whenever you want to stop or start again.
prev: a-home-for-your-apps
next: your-own-ai-agent
---

# Take it all down

*An appendix to [Your own AI agent, from anywhere](../your-own-ai-agent/). Draft: not yet tested end to end.*

You can walk away cleanly at any time, whether you were trying things out, want to start again, or need room for other apps. This page takes the playbook down in reverse order. Claude asks before each removal.

> **Keep your data, or delete it?**
>
> Removing an app keeps its data on your machine, so setting it up again under the same name picks up where you left off: your agent's memory, your bookmarks, your gateway's spending history. Deleting the data is a separate, deliberate step, at the end of each section. If you're on a virtual machine and want everything gone, skip to [The shortcut](#the-shortcut-delete-the-virtual-machine).

## 1. Your bookmarks

> Remove linkding.

Its bookmarks stay on your machine unless you also say: *"and delete its data"*.

## 2. Your agent

> Remove my agent, and revoke its gateway key.

Its memory and conversations stay on your machine unless you also ask to delete its data. Its gateway key stops working at once, so nothing can spend on its behalf.

## 3. Your AI gateway

> Remove my AI gateway.

Your provider keys stay stored with Edgible, ready if you set a gateway up again. To remove those too:

> Delete my stored AI keys from Edgible.

If you won't use them again, also revoke them at each provider: DeepSeek, Gemini, and any others you added. That's done on their websites, and only you can do it.

## 4. The connector

The connector is how Claude reaches your Edgible, so it comes down last, in two places:

1. **In Claude:** Settings, Connectors, then remove **Edgible**.
2. **On your machine:** in Claude Code on your own computer, say:

   > Remove the Edgible connector from my edgible-vm.

## 5. Edgible itself (optional)

To take the machine off your Edgible account and uninstall Edgible's agent from it, in Claude Code:

> Remove Edgible from my edgible-vm, and take it off my account.

Your Edgible account stays, with nothing in it, ready if you come back.

## The shortcut: delete the virtual machine

If you followed [Getting a machine](../getting-a-machine/) and made a virtual machine, you can remove everything on it in one go. In Claude Code:

> Delete the edgible-vm virtual machine.

Then tidy the two things that live outside it: the connector in Claude's settings (step 4.1), and the machine's entry in your Edgible account (*"Take my edgible-vm off my Edgible account"*). Your stored AI keys stay with Edgible until you delete them (step 3).

## What you've just done

You've taken it all down, and you chose what happened to your data. Nothing was locked in: no export to ask for, no account to plead with. That's what owning it means.

<details>
<summary>Prefer to do it by hand?</summary>

Each app's card README ends with a Tear down section, the same steps in order: unpublish, stop, delete the data, remove the card. `edgible secret delete <name>` removes a stored key; `edgible device` and `edgible agent` commands take a machine off your account and uninstall the agent; `multipass delete --purge edgible-vm` removes the virtual machine.

</details>
