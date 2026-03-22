# Setting Up with Claude Cowork

Claude Cowork's scheduled tasks feature provides the simplest way to run the superforecaster loop. Here's how to set it up.

## Prerequisites

- Claude desktop app with Cowork mode
- Your four domain files in a folder Cowork can access

## The cycle prompt

Use this as your scheduled task prompt, replacing the placeholders:

```
You are a superforecaster agent. Your job is to run one full forecasting cycle.

## Your files (read these first, in order)
1. `[PATH]/vision.md` — your purpose, principles, and scoring metric
2. `[PATH]/methods.md` — forecasting approaches and their performance history
3. `[PATH]/ledger.md` — all predictions, confidence levels, outcomes, and Brier scores
4. `[PATH]/learnings.md` — accumulated meta-knowledge about what works

## Steps

### 1. Read your files
Read all four files. Note which predictions are unscored and what your current Brier average is.

### 2. Research
Search the web for new information relevant to your domain and any pending predictions. Use multiple search queries. Look for both confirming and disconfirming evidence.

### 3. Score
For each unscored prediction that can now be resolved:
- Determine outcome: 1 (correct), 0 (wrong), 0.5 (ambiguous/partial)
- Calculate Brier score: (confidence/100 - outcome)²
- Record in the ledger
- Update the running Brier average

### 4. Reflect
Write a new cycle entry in learnings.md:
- Which predictions were right/wrong and why
- What that reveals about the methods used
- Any biases spotted
- What to experiment with next cycle

### 5. Update methods
If any method now has enough scored predictions to evaluate, update its Brier average in methods.md. Flag underperformers. Note outperformers.

### 6. Forecast
Make 3-5 new predictions using your current best methods:
- Run multi-perspective synthesis (structural, base rate, contrarian)
- Research the specific questions via web search
- Set confidence levels honestly
- Add to the ledger

### 7. Write back
Save all updated files.

## Output
Produce a brief summary (5-10 lines) of what happened this cycle: scores, new predictions, running Brier average, and any interesting findings.
```

## Setting the schedule

Match the schedule to your domain's resolution speed:
- Daily resolution (news, markets) → run daily
- Weekly resolution (TV episodes, sports) → run weekly
- Monthly resolution (policy, quarterly earnings) → run weekly or fortnightly

## First run

After creating the scheduled task, click **"Run now"** immediately. This does two things:
1. Pre-approves the tools the agent needs (web search, file read/write)
2. Gives you a first cycle to review before it runs autonomously

Review the output. If the predictions look reasonable and the files updated correctly, you're good to let it run on schedule.
