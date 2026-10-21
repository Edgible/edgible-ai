---
title: Getting a machine
description: Where to run Edgible if you have no spare computer: a virtual machine on your own computer, or a small cloud server, with your AI assistant doing the setup.
---

# Getting a machine

Edgible runs on a computer you control. If you have a spare one, use that. If not, here are the other ways, and your AI assistant can do most of the work for each.

| | Good for | Stays on | Cost |
| --- | --- | --- | --- |
| **A spare computer** | Anything | If you leave it on | Free |
| **A virtual machine on your own computer** | Trying Edgible, learning, testing | Only while your computer is on and awake | Free |
| **A small cloud server** | A website or apps other people rely on | Always | A few dollars a month and up |

## What Edgible needs

Whichever you choose, tell your AI these, so it gets them right:

- **Ubuntu 24.04 or 26.04,** or a Mac. Not WSL on Windows: Edgible can't publish apps from there yet.
- **Memory:** 2 GB for a website, 4 GB for an AI agent.
- **Disk:** 20 to 30 GB free.
- **Internet out, and no ports in.** Edgible connects out, so there's nothing to open in a firewall or router. If your AI offers to open a port for Edgible, say no.
- **On when you need it.** For apps other people use, a machine that stays on.

## A virtual machine on your own computer

A virtual machine is a whole computer running inside yours. We use Multipass, Canonical's free tool for Ubuntu virtual machines, on a Mac, Windows or Linux. In Claude Code on your computer, say:

> Create an Ubuntu 26.04 virtual machine with Multipass, named edgible-vm, with 2 CPUs, 4 GB memory and 30 GB disk. Install Multipass first if it isn't here. Don't open any ports.

It takes a few minutes. Then, in [Get Edgible running](../get-edgible-running/), Claude Code stays on your computer and sets up the virtual machine from there. Say this in place of step 3:

> Set up Edgible on the Multipass virtual machine named edgible-vm, so I can run my own apps there.

The virtual machine runs while your computer is on and awake. For anything other people rely on, choose a spare computer or a cloud server instead.

**What you've just done:** you have a whole Ubuntu server, free, running inside your own computer, without changing anything on your computer itself. Not sure about it? Say *"Delete the edgible-vm"*, and it's gone. Like it? When other people come to rely on your apps, your AI can move them to a machine that stays on, data and all.

## A small cloud server

A server you rent by the month, from Hetzner, DigitalOcean or AWS Lightsail for example. You make the account and pay; your AI walks you through the rest:

> Help me create a small Ubuntu 26.04 server at Hetzner with 4 GB memory. Sign-in with an SSH key only, and no inbound ports except SSH. I'll install Edgible on it.

Then, in [Get Edgible running](../get-edgible-running/), say this in place of step 3, with your server's address:

> Set up Edgible on my server, which I reach with ssh root@203.0.113.10, so I can run my own apps there.

## A spare computer

An old laptop or desktop works well. A Mac can run Edgible as it is: just set it not to sleep. A PC is best wiped and given Ubuntu:

> Help me put Ubuntu 26.04 on my old PC, so it can run Edgible all the time. I have a USB stick.

Then follow [Get Edgible running](../get-edgible-running/) on that computer, or from your own, as above.
