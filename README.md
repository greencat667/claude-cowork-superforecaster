# Superforecaster

An autonomous forecasting agent that makes predictions, scores them, and iteratively improves its own methods — inspired by [autoresearch](https://github.com/karpathy/autoresearch), the [Ralph loop](https://github.com/snarktank/ralph), and [MiroFish](https://github.com/nikmcfly/MiroFish-Offline).

## How it works

The agent runs on a simple loop:

```
read state → research → score past predictions → reflect → forecast → write state → sleep
```

Progress lives in files, not in context. Each run starts fresh, reads the current state, does one cycle of work, and writes everything back. Over time, the agent accumulates evidence about which forecasting methods work best for which types of questions, and shifts its approach accordingly.

### The four files

Every forecasting domain uses the same four files:

| File | Purpose |
|------|---------|
| `vision.md` | What to forecast, why, scoring metric, principles, constraints |
| `ledger.md` | Every prediction with confidence, reasoning, outcome, and Brier score |
| `methods.md` | Forecasting approaches ranked by accumulated evidence |
| `learnings.md` | Self-improvement log — what worked, what didn't, bias spotted, method adjustments |

### The loop

Each scheduled cycle:

1. **Read** all four files to understand current state
2. **Research** what's happened since the last cycle (web search, news, data)
3. **Score** any predictions that can now be resolved — calculate Brier scores
4. **Reflect** — update learnings with what worked and what didn't
5. **Forecast** — make new predictions using current best methods
6. **Experiment** — try one new or varied approach and note it
7. **Write** all updated files back

### Scoring

Uses the [Brier score](https://en.wikipedia.org/wiki/Brier_score): `(confidence - outcome)²`

- Confidence: your probability estimate (0.0 to 1.0)
- Outcome: 1 if correct, 0 if wrong
- Lower is better. Perfect = 0. Random guessing = 0.25.

The goal isn't just being right — it's being *well-calibrated*. A 70% prediction that comes true is better than a 95% prediction that comes true, if the underlying uncertainty genuinely warranted 70%.

## Design principles

Borrowed from three sources:

**From autoresearch:** One metric, keep-or-discard. Each method gets scored. If it improves calibration, keep it. If not, discard. No drift.

**From the Ralph loop:** Progress persists in files, not memory. Each run reads state cold, does work, writes back. Context window doesn't matter because knowledge is externalised.

**From MiroFish:** Multi-perspective reasoning. Instead of one chain of thought, generate multiple analytical framings (base rate, dramatic logic, contrarian, structural) and synthesise across them.

## Quick start

### 1. Copy the templates

```bash
cp -r templates/ domains/my-domain/
```

### 2. Edit `vision.md`

Define your forecasting domain, what "better" means, and any domain-specific principles. See [docs/writing-a-vision.md](docs/writing-a-vision.md) for guidance.

### 3. Seed your first questions

Add 5–10 initial predictions to `ledger.md`. These should be concrete, falsifiable, and have a resolution date. See [docs/writing-good-questions.md](docs/writing-good-questions.md).

### 4. Set up the loop

The agent needs a way to run on a schedule. Options:

- **Claude Cowork** — use the scheduled tasks feature (see [docs/cowork-setup.md](docs/cowork-setup.md))
- **Cron + CLI** — run with any LLM CLI tool on a cron schedule
- **GitHub Actions** — trigger on a schedule, use an LLM API to run the cycle
- **Manual** — just run it yourself whenever you want

### 5. Let it run

After a few cycles, check `learnings.md` to see what the agent is discovering about its own methods. Check the running Brier average in `ledger.md` to see if it's improving.

## Example domains

| Domain | Resolution speed | Description |
|--------|-----------------|-------------|
| [For All Mankind S5](domains/for-all-mankind/) | Weekly (episode drops) | Predicting plot events in Apple TV+'s alt-history space drama |

**Other domain ideas:** UK climate policy decisions, tech company earnings/launches, sports seasons, election outcomes, scientific publication results, open source project milestones.

## Adding a new domain

See [docs/new-domain-guide.md](docs/new-domain-guide.md) for a step-by-step walkthrough. The short version:

1. Pick a domain with questions that resolve on a predictable schedule
2. Copy the templates
3. Write a vision doc with domain-specific principles
4. Seed 5–10 initial questions
5. Set up the loop
6. Let it run for a few cycles before tweaking anything

## Contributing

This is an experiment. If you try it on a new domain and learn something interesting about what works, open a PR adding your domain to the `domains/` folder or share your learnings.

## Licence

MIT
