# Perishable Security

**Security built on cost doesn't fail. It expires.**

Most security is a cost argument: an attack is "too expensive" to be worth it. But costs move — compute gets cheaper, models get sharper, techniques get published, flaws get found. So every component whose safety rests on cost has a **trust half-life**: the estimated time until breaking it becomes cheaper than what it protects.

The question is not *"is it secure?"* but **"how long until it isn't?"**

This repository holds the article series that introduces the idea and a starter template for putting it into practice.

---

## The rule in one line

> **Act when the trust half-life drops below the time you need to get away from it.**

```
Required time = Migration time + Protection horizon
Margin        = Half-life (low end) − Required time

Margin < 0                → EXPOSED — act now
0 ≤ Margin < threshold    → AMBER   — plan migration
otherwise                 → GREEN
```

- **Migration time** — honest time to move off the component, set by the *slowest* dependency (oldest system, longest contract, slowest supplier, recovery paths).
- **Protection horizon** — how long the protected thing must stay safe from today. `0` for live authentication; years for confidential data that could be harvested now and decrypted later. This generalises **Mosca's inequality** from quantum risk to every decay force.

---

## Contents

| Path | What it is |
|---|---|
| [`articles/part1-tedium-was-a-lock.md`](articles/part1-tedium-was-a-lock.md) | **The Spark** — AI reverse engineering makes understanding cheap; tedium was a security control |
| [`articles/part2-trust-half-life.md`](articles/part2-trust-half-life.md) | **The Physics** — break-cost falls, payoff rises, response latency decides if you notice |
| [`articles/part3-slides-cliffs-and-the-dark.md`](articles/part3-slides-cliffs-and-the-dark.md) | **The Practice** — watching slides (trend), cliffs (listening post) and the dark (estimation) |
| [`template/trust-register-template.xlsx`](template/trust-register-template.xlsx) | **Trust register** — working template with formulas, dropdowns and colour-coded status |
| [`template/trust-register-template.csv`](template/trust-register-template.csv) | Same register as plain CSV (example rows, computed values) — for diffs, review and import |

---

## Using the template

1. **List components whose security is a cost argument** — encryption, authentication schemes, hardware roots of trust, obfuscation, client-side logic, proprietary protocols.
2. **Give each one owner**, what it protects, and the cost assumption it rests on.
3. **Estimate the half-life as a range** (low–high years) with a confidence level. Direction and rate matter more than decimals.
4. **Estimate migration time honestly** and set the protection horizon.
5. **Record the listening post** (where a sudden break would be heard), whether a **pre-written plan** exists, and the likelihood of a **private, unannounced break**.
6. **Review on a cadence.** One owner. One estimate. One date.

In the `.xlsx`: yellow cells are inputs, grey cells are formulas. The amber threshold and review cadence live in the `Settings` tab.

> ⚠️ **The three example rows (EX-001 to EX-003) are illustrative**, not real estimates for any organisation. Replace or delete them.

### Columns

`ID` · `Component` · `What it protects` · `Owner` · `Security rests on (cost assumption)` · `Dominant decay force` · `Shape` (slide / cliff / both) · `Payoff trend` · `Half-life LOW (yrs)` · `Half-life HIGH (yrs)` · `Confidence` · `Migration time (yrs)` · `Slowest dependency` · `Protection horizon (yrs)` · `Required time (yrs)`* · `Margin (yrs)`* · `Status`* · `Listening post / feed` · `Pre-written plan?` · `Plan ref` · `Private-break likelihood` · `Last review` · `Next review`* · `Notes / sources`

\* computed in the `.xlsx`; stored as values in the `.csv`.

---

## Five questions an auditor could ask

1. Do you have a **trust register** — components whose security is a cost argument, each with an owner?
2. Does each have a **dated half-life estimate** — range, confidence, next review?
3. Do you know your **migration time** for each — honestly, set by the slowest dependency?
4. Are you connected to a **listening post**, with incoming events mapped to the register?
5. Do you have a **pre-written plan** for when each one falls?

Prescribe the obligation. Leave the method to the market.

---

## Status and honesty

This is **v0.1** and deliberately open to attack. The weakest part is the "dark figure" estimate — the likelihood that a component is already broken privately. It is offered as a starting point, not a finished method.

"Half-life" is borrowed for intuition, not as a claim that security decays exponentially. Sometimes it slides; sometimes it falls off a cliff.

**Issues and pull requests are welcome** — especially from cryptography, risk, threat intelligence and regulation.

---

## Related

- **AI Governance Field Kit** — cards G1–G3 apply this principle to AI-assisted reverse engineering. The *Kerckhoffs gap* (G1) is the trust half-life trigger applied to one threat.

## Credits

- **Auguste Kerckhoffs**, *La cryptographie militaire* (1883) — a system must stay safe when the enemy knows how it works.
- **Michele Mosca** — the quantum-risk inequality that this template generalises.
- Cryptoperiod practice in key management.
- **Guilherme Campos** — for the spark.

## Licence

Content and template: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Use, adapt and share — with credit.

© 2026 Rui Soares
