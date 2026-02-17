---
layout: post
title: "Cognitive Debt"
date: 2026-02-16
tags: [AI, Software Engineering]
excerpt: "Build First - Understand Later"
---

![Smilodon Software](/assets/images/smilodon-software.png)
*Smiley the Sabertooth Cat attempts to understand the 8,000 lines of code he just generated*
{: style="text-align: center; color: #999; font-size: 0.9rem;"}

## Build First - Understand Later

Cognitive Debt is the gap between what your code does and how well you understand it

## Abstract

Cognitive debt describes what happens when you take shortcuts in your _understanding_ of your code. AI-assisted development has made it possible to build sophisticated systems faster than any human can comprehend them, creating a new category of risk where software rolls off the production line but humans don't know how it all works under the hood.

* TOC
{:toc}

## Overview

### Everyone Is Already in Debt

In the era of Claude Code everyone is taking some amount of cognitive debt. What does this mean specifically: when you tell Claude to generate an app, in the year 2026 there is a good chance it can one-shot a working prototype. Great! But how much of the generated code do you need to actually read and understand to truly have ownership of this generated software? This may not be a big deal for personal hobby projects, but it will probably be the BIGGEST deal of the rest of the decade for any software engineer that is responsible for shipping code to production.

### Bigger Than Code

And this isn't specific to code. Anyone with access to an LLM can generate a research paper, send a hundred emails, produce an entire codebase — and not reliably know what is inside any of those things. Cognitive debt is a general phenomenon of the AI era. But software is where the consequences are sharpest, so that's where I'll focus.

### Technical Debt: The Original Metaphor

#### Ward Cunningham's Insight

The term cognitive debt is explicitly modeled on the famous term '[technical debt](https://en.wikipedia.org/wiki/Technical_debt)'. Here is an explanation of technical debt by the man who coined the term (from the technical debt wikipedia page): "Shipping first time code is like going into debt. A little debt speeds development so long as it is paid back promptly with a rewrite... The danger occurs when the debt is not repaid. Every minute spent on not-quite-right code counts as interest on that debt. Entire engineering organizations can be brought to a stand-still under the debt load of an unconsolidated implementation, object-oriented or otherwise."— Ward Cunningham

#### Debt as a Tool

Ward captured something important - the debt metaphor works well because in finance debt is a tool. You borrow so you can buy something immediately that you wouldn't be able to buy otherwise. But if you don't pay back your debt there are negative consequences. This inherent tension has always been part of the software development process.

### Cognitive Debt: What's Different

#### The Code Works, But Nobody Understands It

Technical debt implies that there are code optimizations or fixes that are left on the table for expediency. Cognitive debt doesn't make any assumptions that the code is broken - rather it assumes that the code is simply not understood (not even read in the most extreme case). The magnitude of the debt corresponds to how much thinking you need to do to fully comprehend what is happening inside the thing you just generated. Prominent software influencers like [Steve Yegge](https://steve-yegge.medium.com/) have famously claimed to have shipped [beads](https://github.com/steveyegge/beads) without ever opening and reading the code in a text editor.

#### Cognitive Debt in the Before-Times

Cognitive debt was still a problem in the pre-AI before-times. Engineering managers, product owners, many of them never had time to open and read a full codebase, for them the software product was something between a translucent and opaque black box. But most companies always had an engineering team that theoretically covered all of the ground with human understanding. So an individual manager may be in cognitive debt, but all the engineers in aggregate could theoretically explain every line of code.

#### Silent Interest: Bad Decisions from False Confidence

This was a common failure mode for software projects in the before-times: decision makers rarely (or never) cracked open a text editor to peek at the codebase they were responsible for, and the cognitive debt was never paid back. Decision makers would shoot from the hip: "let's model the data this way; let's hire overseas contractors and not give them proper context to understand the tool they're merging code into; let's move fast and break things!". The poor decisions downstream of insufficient understanding would accumulate as a kind of silent interest on the cognitive debt. And then - one day - there is a default. The product breaks and the cognitive debt must be repaid immediately, or your its over.
#### npm install and the Debt We Already Carried


Even the engineers were carrying more cognitive debt than they probably admitted. Nobody was reading the source code of their third-party node modules. Every `npm install` was an act of faith -  a pile of dependencies that your application relied on but that no human on your team had ever actually read. Cognitive debt has always existed at the edges of every codebase, in the dependencies and libraries that no one reads. AI moves that problem to the core of the codebase. Before people weren't reading the libraries - now they aren't even reading the core codebase itself.

#### AI Didn't Invent This Problem — It Removed the Speed Limit

This problem predated the emergence of AI in the application layer. At an old job of mine, contractors would yeet code into our codebase at such a high volume that was impossible for the US team to fully review. It would usually work. The problem was that our team was supposed to own all of that code, and we were under a lot of pressure to sacrifice thorough review for quick merges. The cognitive debt was real in the before-times — we just didn't have a name for it. AI didn't invent this problem, it just removed the last natural speed limit.

#### From Team Problem to Individual Problem

What used to be a problem with teams has now become acutely relevant to the individual. In the before-times output was slow, and humans had to write their code. Naturally, ownership of code was usually traced back to the person who manually wrote it. A single developer could only accrue so much cognitive debt because they could only produce so much code. But now a single person can generate an entire application in an afternoon — and carry a debt load that used to be distributed across an entire team. And at the team level, the problem compounds even further. Anyone from an engineer, to the product manager, to a random HR representative can generate code, and that code can make it into a production codebase. Who owns this code? Who is responsible ultimately for knowing how it works?

#### Engineers as Physicians: Liable for Work You Can't Fully Review

The implications for the profession are significant. Software engineers may increasingly find themselves in a role that resembles a physician managing a large staff of physician's assistants — unable to redo all of their work personally, but still legally and professionally liable for the outcomes. The PA sees the patients and makes judgment calls, but the physician's name is on the chart. In the same way, the AI generates the code and makes implementation decisions, but the engineer's name is on the pull request. Teams will need to figure out how to find the right balance of generating code against understanding how the code works at a granular enough level to debug any problem or add new features.

#### Is There an Optimal Amount of Cognitive Debt?

This raises a question that I think will define the practice of software engineering for the rest of the decade: is there an optimal amount of cognitive debt? Not zero - that would mean never letting an AI outrun your understanding, which throws away the speed advantage entirely. But not infinite either, because at some point you're operating a system you can't debug, extend, or explain. The dial exists. The question is where to set it.

#### The Mortgage Principle: Why Cognitive Debt Can Be Rational

We have never been able to move faster with producing code. Taking out cognitive debt is often rational for the same reason a mortgage is rational - nobody tells you to save up $500k in cash before buying a house. Sometimes the thing you need to build is simply too large to understand fully before you begin. You take out the loan, you move in, and you pay it back over time. But there needs to be a plan to pay it back. Maybe its a week long learning plan. Maybe time is blocked off to read through the different pull requests involved. If this is not done, like tech debt, interest will accrue to the point of metaphorical default - which will probably be some kind of failure in production, with no one knowing who is responsible, who to blame, and who can fix it.

#### The Down Payment: Not All Cognitive Debt Is Equal

Not all cognitive debt is created equal. Just like a bank won't fund a business with no plan, you shouldn't take on cognitive debt without doing your due diligence first. Good cognitive debt has a big down payment: you understand specifically what you want to build and have strong evidence that letting the AI rip will produce something worth learning. Bad cognitive debt is generating the wrong thing and then spending time learning the wrong thing. It's like taking out a loan for a business that instantly fails. The down payment is what separates strategic debt from reckless debt.

#### Loans vs Debt: A Useful Distinction

Not to overly belabor our analogy, but It's worth noting the difference between a cognitive loan and cognitive debt. A loan is a discrete event. You generate an app, you take on a specific obligation. Debt is the state you're in while the loan is outstanding. You can take out multiple loans. They accumulate into a debt load. And like financial debt, the question isn't whether you have any - it's whether you can service it.

#### The Lender Is the Tool

It's worth recognizing who the lender is in this metaphor: the AI itself. Claude, GPT, Codex - these are the banks issuing your cognitive loans. This has a practical implication: if your lender goes down, your line of credit is cut. Anyone who lived through a major model outage while mid-project knows this feeling. It also means you want multiple lenders, for the same reason businesses maintain relationships with multiple banks.

#### Teeing Up the Worked Example

Its not all doom and gloom though. Below I will tell a personal story about some work I did with a client in 2025. I bit off way more than I could chew and was extremely ambitious. I took out a huge cognitive debt, but I paid it back, and I think it was the right move - much better than the alternative. I was tasked with creating an HTMX powered hypermedia frontend for an existing monorepo written in Go. I chose to have Claude far outrun my ability to understand what was going on - and then slowly learned and picked through what I had generated. If I had taken the opposite approach — dug into O'Reilly books to learn Go's template and net/http libraries before writing a line of code — the process would have taken dramatically longer. I generated tens of thousands of lines of code, and eventually paid back that debt in full — manually touching every line of the codebase at some point with a debugger, or at least reading it. I learned a ton and shipped a completed project much faster than if I would have taken a more incremental approach where I understood everything that I shipped.

## Worked Example: HTMX Frontend for a Go Monorepo

### The Brief

In 2025 I was brought on as a contractor by a manufacturing startup to build custom software. My marching orders: build an [htmx](https://htmx.org/)-powered frontend for a monorepo "company brain" written in Go. The frontend would be a feature-rich dashboard that factory floor personnel could use to track and manage their work. It would be seamlessly integrated with the customer ordering system. Most importantly, it needed to compile down to the company brain's single binary — no separate frontend. It also needed to use the go-kit inspired tooling currently in use for the company brain repo; this included a whole lot of auth, logging, and telemetry middleware.

I had been writing Go for almost a year but this was far beyond the scope of anything I had tried to do on my own.

### Failure Mode 1: The O'Reilly Trap

My first mistake was to try to approach this problem by figuring out what I didn't know, what I needed to know (Rumsfeld epistemology — known unknowns), and using O'Reilly books to learn all those things BEFORE starting the project. This was like a farmer in rural India saving up cash for 80 years to buy a tractor. It's clear the man needs a loan.

### Failure Mode 2: Trusting Claude Completely

This was back in the ancient epoch of Opus 3. I thought to myself "Claude has read all the Go books, and all the htmx docs — this should be easy." No — Claude could not decide on any consistent design pattern. Nothing usable was vibed. This was like taking out a loan for a business that instantly fails.

### Success 1: Due Diligence Before Signing the Dotted Line

I found all the htmx tutorials that I could (shoutout [Primagen's Go+HTMX tutorial](https://www.youtube.com/watch?v=x7v6SNIgJpE)), worked through them, and fed the transcripts to Claude. I also did some baby experiments at a much smaller scope. I arrived at some concrete design patterns. This is like due diligence before taking out your loan — I made sure I didn't start vibing until I had strong evidence that letting Claude rip would create something usable.

### Failure Mode 3: Unforeseen Problems and Mounting Interest

I successfully created a gigantic router for all of the HTMX operations, but the net/http library kept throwing me esoteric bugs. While I was paying back my cognitive debt — stepping through request handlers with a debugger, tracing how templates resolved partials, reading net/http source code to understand why my middleware was swallowing errors — I kept asking myself "Did I do this the right way? Is this approach just shitty enough that it won't ultimately work?"

### Success 2: Many Small Loans Beat One Big One

The issues I had with the templates and net/http standard library shifted me to vibing out multiple smaller prototypes to test hypotheses I had about what would and would not work. I couldn't have formed these hypotheses initially because I simply didn't know enough about how htmx would interact with Go's template and net/http libraries. This is an important point: the cognitive debt I had already partially paid back — the understanding I had gained from debugging the first big attempt — was what allowed me to take out smarter, smaller loans the second time around.

### Failure Mode 4: When Your Lender Goes Down

Well shit — vibing tens of thousands of lines of code is expensive. Who knew? Also, the great Claude outage of August-September 2025 made me shift mindsets. The answer: make sure you have MULTIPLE LENDERS. This meant setting up OpenRouter, using OpenCode, exploring Codex when it was released. Just like a business shouldn't depend on a single bank, a developer shouldn't depend on a single AI provider.

### Success 3: The Revolver

A lot of businesses operate on what's called a 'revolver'. This is a monthly provisioning of loans to cover monthly costs. It mitigates the risk of a company having an accidental check bounce due to cash flow issues. My end state with cognitive debt was a kind of revolver of my own, where I started getting my vibe+payback loop into a daily flow. Once I figured out the right balance of down payment + vibe + payback I was cruising, and learning at a very rapid pace. This is what sustainable cognitive debt looks like — not a single massive loan you pray you can repay, but a regular rhythm of borrowing and understanding.

### Success 4: It's Alive

If you've never built a hypermedia frontend that allows you to dynamically sort factory orders without ever even saying the word 'React', I highly recommend that you do it. It's a transcendental feeling. This whole process could have gone so wrong but I ended up building something amazing for my client. I generated tens of thousands of lines of code, and eventually paid back that debt in full — manually touching every line of the codebase at some point with a debugger, or at least reading it.
