# Slides, Cliffs and the Dark

*Perishable Security — Part 3 of 3: The Practice*

---

You can't watch everything.

You can watch enough — if you know what kind of decay you're watching for.

---

Part 1 showed that tedium had been quietly guarding our software, until AI made understanding cheap.

Part 2 drew the general lesson: security built on cost doesn't fail, it expires. Every component has a **trust half-life** — the time until breaking it becomes cheaper than what it protects. The trigger to act is simple: **when the half-life drops below the time you need to migrate away, you're already exposed.**

Which leaves the practical question. How do you watch something decay?

Decay comes in three shapes. Each needs a different kind of watching.

- **Slides** — gradual, predictable. You watch a trend.
- **Cliffs** — sudden, public. You keep a listening post.
- **The dark** — sudden, private. You can't watch it. You estimate it.

## 1. Slides: watch the trend

Most decay is boring. Compute gets a bit cheaper. Models get a bit better. Techniques spread. You can draw the line.

This doesn't need a new tool. It needs a habit.

**Step 1 — Keep a trust register.**
List the components whose security is, at heart, a cost argument: encryption, hardware roots of trust, authentication schemes, anything that relied on being hard to understand. For each: an owner, what it protects, and **how long it would take you to migrate away.**

That last column is the one nobody has. Fill it in honestly. It's usually longer than you think.

**Step 2 — Estimate direction, not decimals.**
You won't get a precise break-cost. You don't need one. Ask: *is it getting cheaper to break this, how fast, and roughly when does it cross what an attacker would gain?* Give a range and a confidence level.

**Step 3 — Test against something fixed.**
Track decay against a stable set of test tasks — *"can a current model recover this kind of logic from this kind of binary?"* — so this year's estimate is comparable with last year's.

Publish the **kind** of test and the method. **Rotate the specific instances.** If a test is dangerous to publish, that's not a reason to hide it — it's a sign the design under test was leaning on secrecy all along.

**Step 4 — Review on a cadence.**
Put a date on every estimate. When the half-life range starts overlapping your migration time, start moving. Not when it breaks. Now.

## 2. Cliffs: keep a listening post

Some decay arrives as an event. A technique is published. A flaw is disclosed. A component's trust half-life goes from years to days overnight.

No trend line warns you. What you need is to **hear it fast** and **already know what you'll do.**

Hearing it fast doesn't require building anything new — at least not in Europe. NIS2 already obliges organisations to take part in a network of national CSIRTs, vulnerability disclosure and threat-intelligence sharing. The listening post exists.

The proposal is modest: treat **"a cost assumption just collapsed"** as a category of intelligence that belongs in that feed — and map incoming events to the components in your trust register.

Knowing what to do means a **pre-written plan per component**: if this falls, what do we switch off, what do we switch to, who decides. Written in calm weather. Not improvised in the storm.

## 3. The dark: estimate what you can't see

Here's the uncomfortable part.

The cliffs you hear about are the ones somebody announced. The most dangerous break is the one nobody announces — sitting quietly in a well-funded lab or a state arsenal.

Your listening post hears the weather. Not the ambush.

You can't detect that. But you're not helpless. **You can estimate how much you don't know.**

Other fields solved this shape of problem long ago:

- **Criminology** estimates the *dark figure* of crime — offences never reported — from what is reported and how reporting behaves.
- **Ecology** estimates how many species a survey *hasn't* found yet, from the pattern of the ones it has.

Security can borrow the same move. We have history: how long capabilities and flaws tend to exist privately before they surface publicly. That lag is a conversion factor — from *"what I've seen"* to *"what's probably already out there."*

The output isn't an all-clear. It's a **shaded band** under your estimates: *"given what's been disclosed, there's a meaningful probability this component is already broken, privately."*

I'll be honest: this is the least mature part of the whole idea. I'm offering it as a starting point, not a finished method.

Tear into it. That's what it's for.

## Kerckhoffs's sixth principle, paid back

In Part 1, I asked you to hold a thought. Kerckhoffs's sixth principle: a system must be easy to use, without wearing out the people who run it.

All of the above fails the moment it becomes a burden nobody carries. Part 2 called it **response latency**: a perfect estimate nobody reads has a half-life of zero.

So keep the human end brutally simple:

**One owner. One estimate. One date.**

Per component. Reviewed. Acted on.

And don't forget the other human — the customer at the end of the chain. When the fakes become perfect, the last defence isn't their vigilance. It's the promises you keep: *we will never call you and ask you to move money.* Invariants, not spot-the-difference.

## What a regulator could actually ask

No new tool mandated. No vendor chosen. Just five questions an auditor can check:

1. **Do you have a trust register** — components whose security is a cost argument, each with an owner?
2. **Does each have a dated half-life estimate** — range, confidence, next review?
3. **Do you know your migration time** for each — honestly, set by the slowest dependency?
4. **Are you connected to a listening post**, with incoming events mapped to the register?
5. **Do you have a pre-written plan** for when each one falls?

Prescribe the obligation. Leave the method to the market. That's how it ages well — and how it slots into machinery that already exists, instead of competing with it.

## The end, which isn't one

Security was never a finish line. It's a metabolism.

Every static control we inherited — the obscurity, the certification, the passed audit — was a photograph pretending to be a guarantee. What I'm proposing is to replace photographs with a pulse.

It never stops. Like life: always running. So we might as well run, and do it properly.

This series began with a colleague mentioning a wave of AI reverse engineering. It ended somewhere much bigger. I suspect parts of it are wrong in interesting ways.

If you work in cryptography, risk, threat intelligence or regulation: I'd genuinely like to know which parts.

---

*Part 1 — The Spark: Tedium Was a Lock.*
*Part 2 — The Physics: Trust Half-Life, the Shelf Life of Security.*

*Thanks to Guilherme Campos for the spark that started all three.*
