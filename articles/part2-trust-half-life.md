# Trust Half-Life: The Shelf Life of Security

*Perishable Security — Part 2 of 3: The Physics*

---

Security doesn't fail. It expires.

We just never print the date on the label.

---

In Part 1, AI-assisted reverse engineering showed us that tedium had been quietly working as a security control — and that it's about to stop.

But the real lesson wasn't about reverse engineering. It was this:

**Almost all security is a cost argument.** And costs move.

A lock is "secure" when picking it costs more than what's behind the door. Cryptography is "secure" when breaking it would take more compute than anyone can afford. Obscurity was "secure" when understanding was too expensive to bother.

Every one of those is a ratio between two things that change over time.

Which means security isn't a state you reach. It's a quantity that decays.

## The idea in one line

**Trust half-life:** the estimated time until a component's break-cost falls below what an attacker would gain by breaking it.

Not *"is it secure?"* — that question has no date on it.

**"How long until it isn't?"**

A word of honesty: I'm borrowing "half-life" for the intuition, not the maths. Nobody has shown that security decays exponentially, like a radioactive isotope. Sometimes it slides. Sometimes it falls off a cliff. The word is a reminder that **decay is the default**, not a promise about its shape.

## A break-cost, a payoff and a response time walk into a bar

The barman says: *"We close before any of you agree on when."*

Those three are the whole physics. Let's take them one at a time.

### 1. Break-cost falls

The cost of breaking something drops, driven by four forces:

- **Cheaper compute** — what took a data centre takes a laptop, eventually.
- **Better models** — AI turns expert work into a prompt. (Part 1's whole story.)
- **Published techniques** — once someone shows how, everyone can.
- **Discovered flaws** — a bug turns "very hard" into "trivial" overnight.

The first three are **slides**: gradual, roughly predictable, you can draw a trend line.

The fourth is a **cliff**: sudden, unpredictable, and indifferent to your trend line.

Any honest model of decay has to handle both.

### 2. Payoff drifts up

Here's the part that's easy to miss: **a component can lose security without getting any weaker.**

If what it protects becomes more valuable — more money flowing through it, more data, more critical infrastructure depending on it — then more attackers care, and they'll pay more to break it.

The lock didn't change. The prize behind the door got bigger.

So trust half-life shrinks from both ends: break-cost sliding down, payoff creeping up. The moment they cross is the moment the component stops being worth trusting.

### 3. Response latency decides if you notice

The third force isn't about the component at all. It's about **you.**

Someone has to watch the two curves. Someone has to read the estimate, believe it, and act. Every week between "the curves crossed" and "we started migrating" is exposure.

A perfect estimate that nobody reads has an effective half-life of zero.

This is where people come in — not as a decay force on the lock, but as the ones who decide whether anyone's watching it.

## The trigger

So when do you act?

Not when the component breaks. By then you're already late.

You act when **the trust half-life drops below the time it would take you to migrate away.**

If moving off a component takes you three years, and your best estimate says it has four years of trust left, you're fine — barely. When that estimate drops to two years, you are already exposed. You just don't feel it yet.

Migration time is the hidden variable. It's the one most organisations never measure, and it's usually longer than anyone admits — because it's set by the slowest system, the oldest contract, the supplier who'll "get to it next quarter."

## None of this is new. Good.

If this sounds familiar, it should. Pieces of it already exist:

- **Cryptoperiods.** Cryptographers have long given keys an expiry date and rotated them before they're likely to be broken. Key lengths once considered safe were retired as factoring got cheaper.
- **Mosca's inequality.** Michele Mosca framed the post-quantum problem almost exactly this way: if the time your data must stay secret, plus the time you need to migrate, exceeds the time until a quantum computer can break your encryption — you have a problem *today*, not later.

That's the trust half-life trigger, applied to one threat.

The move here is to **generalise it**: from keys to whole components, from quantum to every decay force, and from a cryptographer's private discipline to something boards, auditors and regulators can ask about.

Because right now, most organisations treat trust as a box ticked at certification — not a quantity that ages.

## What this changes

Three shifts, if you take it seriously:

1. **Every "secure" claim gets a date.** Not "this is secure" but "we estimate this holds for N years, reviewed on X."
2. **Migration time becomes a security metric.** How fast you *can* move matters as much as how strong you are today.
3. **Monitoring replaces certification as the core activity.** A certificate is a photograph. Trust half-life is a pulse.

## The obvious objection

*"You can't measure break-cost precisely."*

Correct. You can't.

But you don't need precision to know a slide is happening, and you don't need precision to compare it with your migration time. You need direction, rate, and an honest range.

And then there are the cliffs. And the breaks nobody announces — the ones sitting quietly in someone's lab or someone's arsenal.

How do you watch a decay you can only partly see?

That's Part 3.

---

*Part 1 — The Spark: Tedium Was a Lock.*
*Part 3 — The Practice: watching the slides, the cliffs, and the dark.*

---

**Further reading**
- Michele Mosca, on the timeline of quantum risk and migration (Mosca's inequality).
- Auguste Kerckhoffs, *La cryptographie militaire* (1883) — see Part 1.
