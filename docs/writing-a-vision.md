# Writing a Vision Document

The vision doc is the agent's purpose statement. It answers: what are we forecasting, how do we know if we're getting better, and what are the rules?

## What to include

**Purpose** — one paragraph on the domain and why it matters. This grounds the agent. Without it, the loop has no direction.

**Resolution schedule** — how often do questions get answered? This determines cycle frequency. If questions resolve daily, run the loop daily. If weekly, run weekly. Match the loop to the feedback speed.

**Domain-specific principles** — generic superforecasting principles (think in probabilities, use base rates, seek disconfirming evidence) are included by default. Add principles specific to your domain. For example:
- TV predictions: "Never seek spoilers. Distinguish dramatic satisfaction from narrative probability."
- Politics: "Weight institutional incentives over rhetoric. Track what politicians do, not what they say."
- Tech: "Announced ≠ shipped. Weight a company's execution history over its press releases."
- Sports: "Injuries and fatigue are underweighted in public predictions."

**Constraints** — what should the agent NOT do? Off-limits information sources? Ethical boundaries? This prevents the loop from drifting into undesirable territory.

## Common mistakes

- Making the vision too broad. "Predict the future" isn't a vision. "Predict UK climate policy decisions in the next 6 months" is.
- Forgetting constraints. An unconstrained agent will use whatever information it can find, including things you might not want it to.
- No resolution schedule. If you don't know when predictions resolve, you can't score them, and the improvement loop never starts.

## Example visions by domain

**Climate policy:** Predict UK government climate policy decisions (consultations, targets, planning decisions) over the next parliamentary session. Score monthly. Principles: weight institutional incentives, track the gap between stated ambition and delivery track record.

**Tech industry:** Predict product launches, acquisitions, and earnings surprises for the top 10 tech companies. Score quarterly. Principles: announced ≠ shipped, weight execution history, track the gap between demo and GA.

**Sports:** Predict Premier League match outcomes for the 2026-27 season. Score weekly. Principles: home advantage is real but overrated, recent form matters more than season average after matchday 10.
