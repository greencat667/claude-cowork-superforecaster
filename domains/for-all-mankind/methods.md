# Forecasting Methods

This file tracks the approaches the agent uses when forecasting. Each method is rated based on accumulated Brier score evidence. Update after each scoring cycle.

---

## Current Best Methods (ranked by evidence)

*No evidence yet — season starts 27 March 2026. Initial rankings based on superforecasting literature.*

### 1. Reference Class Forecasting
**What:** Ask "what usually happens in shows like this at this point in a season?" TV dramas follow recognisable structures — mid-season crises, penultimate-episode reversals, finale resolutions. Use the base rate for the genre.
**When to use:** Episode-level predictions, character survival, plot beats
**Evidence:** Untested — favoured in literature for reducing narrative bias
**Current Brier avg:** —

### 2. Multi-Perspective Synthesis
**What:** Generate 3 distinct analytical framings before settling on a prediction:
  - *Dramatic logic:* What would be most satisfying narratively?
  - *Base rate:* What typically happens in sci-fi dramas at this story beat?
  - *Contrarian:* What's the case *against* the obvious prediction?
Then synthesise — if all three converge, confidence can be higher. If they diverge, widen the uncertainty.
**When to use:** Major arc predictions, character fate questions
**Evidence:** Untested — derived from MiroFish multi-agent reasoning pattern
**Current Brier avg:** —

### 3. Trailer/Promo Analysis
**What:** Analyse official trailers, clips, and cast interviews for signal. What has Apple TV shown? What have cast members said (or conspicuously avoided saying)?
**When to use:** Pre-season predictions, episode previews
**Evidence:** Untested
**Current Brier avg:** —

### 4. Writer Room Pattern Recognition
**What:** Track how the show's writers have handled similar situations in previous seasons. Ronald D. Moore's patterns (from BSG and FAM) tend toward: earned consequences, long-delayed payoffs, character deaths that serve the theme.
**When to use:** Season-level arc predictions
**Evidence:** Untested
**Current Brier avg:** —

### 5. Community Signal
**What:** After episodes air, search Reddit (r/ForAllMankind) and review sites for the dominant fan theory. Then ask: is the crowd right or is this a case where obvious predictions are being set up to be subverted?
**When to use:** Mid-cycle updates, between episodes
**Evidence:** Untested
**Current Brier avg:** —

---

## Retired Methods
*None yet*

---

## Methods to Try
- Sentiment analysis of character dialogue patterns across seasons
- Structural analysis (episode number as signal — ep 4, 8, and 10 tend to be pivot points)
