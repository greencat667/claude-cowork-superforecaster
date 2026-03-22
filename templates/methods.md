# Forecasting Methods

Tracks the approaches the agent uses when forecasting. Each method is rated based on accumulated Brier score evidence. Update after each scoring cycle.

---

## Active Methods (ranked by evidence)

### 1. Reference Class Forecasting
**What:** Ask "what usually happens in situations like this?" Find the base rate before adjusting for specifics.
**When to use:** Any prediction where historical parallels exist.
**Evidence:** Untested
**Current Brier avg:** —
**Predictions scored:** 0

### 2. Multi-Perspective Synthesis
**What:** Generate 3+ distinct analytical framings before settling on a prediction:
  - *Structural:* What do the underlying incentives/mechanics suggest?
  - *Base rate:* What usually happens in situations like this?
  - *Contrarian:* What's the case *against* the obvious prediction?
If all framings converge, confidence can be higher. If they diverge, widen the uncertainty.
**When to use:** Important or complex predictions.
**Evidence:** Untested
**Current Brier avg:** —
**Predictions scored:** 0

### 3. Source Triangulation
**What:** Find 3+ independent information sources. Weight them by reliability and recency. Look for convergence and divergence.
**When to use:** When web research is the primary input.
**Evidence:** Untested
**Current Brier avg:** —
**Predictions scored:** 0

### 4. Trend Extrapolation
**What:** Identify the current trajectory and ask whether there's a reason to expect it to change. Most things continue their current trend unless there's a specific disruption.
**When to use:** Predictions about ongoing processes (polls, metrics, adoption curves).
**Evidence:** Untested
**Current Brier avg:** —
**Predictions scored:** 0

### 5. Pre-Mortem Analysis
**What:** Assume the prediction is *wrong*, then work backwards to explain why. What would have to be true for this to fail? If the failure story is plausible, lower confidence.
**When to use:** Any prediction where you feel very confident (80%+) — as a check on overconfidence.
**Evidence:** Untested
**Current Brier avg:** —
**Predictions scored:** 0

---

## Retired Methods
*Methods moved here when evidence shows they consistently underperform.*

---

## Methods to Try
<!-- Add new ideas here. The agent should try one new method per cycle. -->
- Domain-specific method: [define based on your forecasting area]
