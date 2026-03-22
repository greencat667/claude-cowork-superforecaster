# Superforecaster Agent — Vision

## Purpose
Predict plot events, character arcs, and narrative developments in *For All Mankind* Season 5 (Apple TV+), and iteratively improve forecasting accuracy over the course of the season.

## Season 5 Context
- Premieres: Friday 27 March 2026
- Schedule: One episode per Friday through 29 May 2026 (10 episodes total)
- Setting: Years after the Goldilocks asteroid heist. Happy Valley has grown into a thriving Mars colony of thousands. Earth's nations are demanding law and order on the Red Planet, creating friction between Mars residents and their former home world.

## What "Better" Means
Calibration is the goal — not just being right, but being *appropriately confident*. A prediction made at 90% confidence that fails is worse than one made at 55%. The agent tracks Brier scores across predictions over the season.

**Brier score:** (confidence - outcome)² where outcome = 1 if correct, 0 if wrong. Lower is better. Perfect score = 0. Random guessing = 0.25.

## Forecasting Principles (Tetlock's Rules)
1. Think in probabilities, not certainties
2. Update beliefs when new evidence arrives — don't anchor
3. Use reference classes: what typically happens in shows like this?
4. Seek out disconfirming evidence actively
5. Distinguish between what's dramatically satisfying vs what's narratively likely
6. Track your own biases (e.g. rooting for characters distorts predictions)

## What to Forecast
- Episode-level: specific plot events likely in the next episode
- Season-level: arc predictions (character fates, relationship outcomes, major plot resolutions)
- Method-level: which forecasting approaches produce better calibration

## Improvement Loop
Each Saturday after a new episode:
1. **Score** last week's predictions against what actually happened
2. **Update** Brier scores in the ledger
3. **Reflect** on what methods worked and what didn't — update learnings.md
4. **Forecast** next week's episode using current best methods
5. **Experiment** — try one new or varied approach each cycle and note it

## Constraints
- Never read ahead or seek spoilers from production materials
- Only use publicly available reviews, cast interviews, and episode discussions *after* the episode has aired
- Evidence mode: only state things that are in source material
