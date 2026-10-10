# Tedium Was a Lock

*Perishable Security — Part 1 of 3: The Spark*

---

For decades, one of our best security controls was boredom.

Nobody wrote it down. Nobody audited it. And it's about to stop working.

---

Last week, Guilherme Campos told me about a wave he'd been watching: frontier AI models getting very good at reverse engineering — taking compiled software apart and explaining what it does.

For now, people are mostly playing. Pulling games apart. Rebuilding them inside other games. Having fun.

Play is how capabilities announce themselves. It is rarely how they stay.

So the question that kept me up: **what happens to security when understanding software becomes cheap?**

## The lock nobody listed

Reverse engineering was always possible. It was also slow, expensive, and dull.

It needed rare people, weeks per binary, and a tolerance for assembly language that most humans reasonably lack.

That dullness was doing a job. **Tedium was a security control.** It just never made it into the risk register.

Look at where it was holding things up:

- secrets tucked inside apps — keys, credentials — safe mainly because finding them was a chore;
- business rules enforced in the client, safe because nobody would bother to read them;
- proprietary protocols in industrial and banking systems, safe because they were obscure;
- obfuscated code — tedium, deliberately manufactured.

None of this was foolish. When understanding was expensive, relying on that expense was a reasonable bet. Hardly anyone predicted the price would fall off a cliff.

But the bet is being called. When a model can read the code and explain it back, tedium isn't a lock anymore.

It's a slightly longer queue.

## The fake with no seams

The obvious worry: attackers find bugs faster. Real.

The subtler one is about people.

We spot fake apps by their seams. A clumsy logo. An odd error message. A flow that doesn't quite feel like our bank.

Those seams exist because faking something well was hard.

Make understanding cheap, and the seams disappear. A clone built from full knowledge of the original can match the screens, the wording, the timing — and talk to the real backend while it does.

The last human heuristic — *"this doesn't feel right"* — goes quiet exactly when we need it.

## A Dutchman saw this in 1883

None of this would surprise **Auguste Kerckhoffs**.

In 1883, a linguist teaching German in Paris published two articles on military cryptography. His most famous principle: **a system must not depend on its own secrecy. It must stay safe even when the enemy knows exactly how it works.**

Claude Shannon later compressed it to five words: *the enemy knows the system.*

For 140 years, we applied this to ciphers. Everything around the cipher — the app, the protocol, the business logic — got a quiet exemption, because knowing it was costly.

The exemption has expired. Kerckhoffs now applies to the whole application.

(He wrote a sixth principle too, less famous and just as prophetic: a system must be easy to use, without wearing its users out. Hold that thought. It matters when the attacker stops fooling the software and starts fooling the person.)

## What still holds

The answer is old, in new clothes. Stop asking *"can they understand it?"* Start asking:

**"If they understood everything, what would they still be missing?"**

Whatever answers that is your real security:

- a key locked in hardware they can't extract;
- a login that only works on the genuine site, however perfect the fake;
- a payment confirmation bound to the exact amount and payee;
- rules enforced on the server, not the client.

**Readable, not actionable.** Let them read every line. Make reading insufficient.

## Can't we just lock the capability up?

Partly, and for a while. Labs and regulators can restrict who gets it.

But capabilities spread — through open models, through copies, through whichever provider restricts least. By recent estimates, the best open models trail the closed frontier by months, not years.

So restriction is a clock, not a wall. It buys time. What matters is whether we spend that time fixing what tedium used to protect.

> *The question isn't how long the gate holds. It's how long you're open after it falls.*

## The trapdoor

And here's where the floor gave way.

Everything above rests on one idea: **security that depends on cost.**

Tedium was cost. Obscurity was cost. Even the strong answers — hardware keys, cryptography — come down to making attacks cost more than they're worth.

But costs move. Compute gets cheaper. Models get sharper. Techniques get published. Flaws get found.

So this was never really a story about reverse engineering. Reverse engineering was just the first place the floor creaked.

If security is cost, and cost decays, then **security is perishable.**

And perishable things need a date on the label — and someone checking it.

That's Part 2.

---

*Part 2 — The Physics: why security built on cost decays, and what decays it.*
*Part 3 — The Practice: how to watch the decay before it bites — including the parts you can't see.*

*Thanks to Guilherme Campos for the spark.*

---

**Sources**
- Auguste Kerckhoffs, *La cryptographie militaire*, *Journal des sciences militaires*, January–February 1883.
- Epoch AI, "Open models lag state-of-the-art closed models by 4 months" (May 2026): https://epoch.ai/data-insights/open-closed-eci-gap
