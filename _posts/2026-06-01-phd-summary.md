---
layout: post
title: CAVA in a Nutshell
date: 2026-06-01 16:00:00
description: Summarising my PhD in <1000 words
tags: CAVA, PhD
categories: posts
thumbnail: ../assets/img/phd_summary_thumbnail.jpg
---

If you've looked into AI safety research, you've probably come across the term *value alignment* at some point. But what exactly does it mean to have "value-aligned" AI? And how do we get there? 

These were the driving questions behind my PhD, **CAVA for Value Alignment: a Neuro-Symbolic Framework from Text to Decisions**, which I finished this year. Having finished the PhD this year and with a postdoc starting soon, I wanted a way to explain the research quickly and clearly for anyone interested. That's what this blog post is for. So, in 1000 words or less, let's look at what CAVA is.

## Why is Value Alignment so Important and Difficult?

AI is everywhere now, whether we like it or not. That's why it's critical that the people developing AI systems build them so that they can reflect our **values**: what we humans care about, and want to see systems support. We can call a system that supports values well **value-aligned**.

But values are tricky things:
1. They are **abstract**. You can't explain a value like 'fairness' without referencing something more real.
2. They are **subjective**. Ask three people what 'fairness' means and you'll get ten different answers.
3. They are **contextual**. Being fair when you're playing sports is very different to being fair in a court of law. Different contexts also prioritise values in different ways.

Taking messy concepts like values and trying to build a computer system with them in mind is hard enough. Trying to do so while also considering all the different **stakeholders**, like developers, users, regulators, etc., and their different values and priorities, and you have a real challenge on your hands.

Let's take an example and say I'm building some automated surveillance in the European Union. I know I want my system to be fair, safe, and respect people's privacy, because those are values promoted by the EU AI Act. So how can I go about being value-aligned when I'm making AI-based security cameras, that might be scanning and identifying people without their knowledge or consent? 

## Designing Value-Aligned Systems

Building value-aligned systems isn't a new problem. Despite the complex nature of values, we've managed to develop numerous systems that satisfy stakeholders. What makes building value-aligned AI systems different comes down to the *level of autonomy* and *scope of problems* we apply AI systems to. When we take a general AI system like ChatGPT and try to use it on a wide range of problems with minimal oversight, problems arise quickly.

To try and help mitigate this, different groups have published *thousands* of policy guidelines for AI developers on what value-aligned AI systems should look like. While this gives developers guidance for constraining their systems, interpretation of these texts is needed. Additionally, developers also have to make their systems align with pre-existing policies. If doctors can't ask patients about their love life without a good reason, then new systems aren't suddenly allowed to just because they use AI.

As you can imagine, that's a lot of material to understand for developers to digest. Not helping is that these texts aren't always written efficiently: some of them conflict, some of them overlap, and many of them can turn out to be irrelevant. It's a big challenge for even the most upstanding developers to understand all of this information. 

Continuing our example, the EU AI Act contains 306 different sections. Determining which sections are relevant to automated surveillance can be surprisingly tricky, so as a developer I probably need to check everything to be safe and compliant. And on top of that, I need to understand all the other policies about building AI surveillance systems, which means I need to find them in the first place. Yikes!

This kind of challenge is what CAVA has been built to address.

## CAVA for Value Alignment

**Contextual Argumentation for Value-based Assessment**, or **CAVA**, is my framework for translating policy guidelines and other texts into structured value representations that support reasoning by both humans and AI. 

![CAVA pipeline from policy text through neural extraction and symbolic reasoning to design guidance and AI decision support.](../assets/img/cava_infographic.png, "CAVA pipeline: [P]olicy texts are processed by a neural extraction module to produce CAVA models, which are then used for symbolic reasoning to provide design guidance for humans and AI decision support.")

CAVA combines **neural** and **symbolic** AI to bridge unstructured policy text with structured decision-making. First, a large language model (LLM) scans text to identify relevant values, the stakeholders they apply to, and the actions or design choices that support them. Information from multiple documents can then be merged into concise value guidelines while preserving links back to the original sources.

We represent this information as *CAVA models*: graphs connecting high-level values to actions and design choices for different stakeholders. For example, here is an excerpt from the law enforcement stakeholder CAVA model in our surveillance problem, which we generated during the PhD.

![Excerpt of a CAVA model linking higher-order values such as benevolence and security to more specific values and design requirements.](../assets/img/cava_law_enforcement.png, "Excerpt of a CAVA model showing how values in the EU AI Act connect to design requirements for law enforcement use of AI surveillance.")

These models can be read by humans and machines alike. We can reason over these models using a symbolic argumentation framework that produces transparent, structured justifications for decisions.

In practice, CAVA serves two purposes. For developers, it summarises stakeholder values and highlights potential trade-offs between different design choices. This reduces the time spent trying to understand stakeholder needs, streamlining the design of systems with stakeholder values in mind. 

For AI systems, CAVA can retrieve relevant policy information to augment responses and support the generation of design strategies grounded in stakeholder values. It can also reason directly about different options and their value trade-offs, providing transparent justifications for its recommendations.

In short, CAVA condenses key value information from complex documents into concise representations, bridging the gap between policy guidance and practical decision-making.

## Wrapping Up

So there you have it, my PhD thesis in 1000 words or less. CAVA has been an epic journey for me in exploring different disciplines and approaches to AI, and finding out how they can fit together on the road to value alignment. While it's early days for CAVA as a value alignment tool, I'm excited to see how it develops going forwards.

If I've piqued your interest, then be sure to check out my bibliography page for the CAVA research I published in my PhD.
