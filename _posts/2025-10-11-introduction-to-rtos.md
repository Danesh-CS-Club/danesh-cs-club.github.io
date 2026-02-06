---
layout: post
title: Introduction to RTOS
date: 2025-10-11 18:00:00 +0330
categories: lectures embedded rtos
tags: real-time concurrency
toc: true
---

With the growing requirement for predictability and determinism in latest embedded systems and time-critical applications, general-purpose operating systems cannot guarantee behavior. This introductory session focuses on Real-Time Operating System (RTOS), terminologies like tasks, scheduling, interrupts, and priorities.

An important part is how RTOS treats concurrency and threading — different tasks execute “at the same time” (at least apparently) using threads, and the scheduler ensures important tasks get CPU time whenever they need it, no matter what else is going on. Unlike normal OSes, no delays are allowed.

**Article / Repo:** https://github.com/Danesh-CS-Club/rtos-intro  
**Recorded Conference:** [Coming soon / Insert YouTube link]  
**Lecture given by:** Ryan Samaeian
