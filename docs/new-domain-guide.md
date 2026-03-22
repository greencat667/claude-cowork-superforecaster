# Adding a New Forecasting Domain

Step-by-step guide for setting up the superforecaster on a new topic.

## Step 1: Pick your domain

Good domains for this system share three qualities:
- **Regular resolution** — questions get answered on a predictable schedule (weekly episodes, quarterly earnings, monthly policy announcements). Without regular feedback, the improvement loop stalls.
- **Researchable** — there's publicly available information to reason about. The agent needs signal, not just vibes.
- **You care about it** — you'll be reviewing predictions and judging quality. If you're bored by the domain, you won't notice when the agent drifts.

## Step 2: Copy the templates

```bash
cp -r templates/ domains/your-domain-name/
```

## Step 3: Write your vision

Edit `domains/your-domain-name/vision.md`:
- Define the domain scope (narrow is better than broad to start)
- Set the resolution schedule
- Add domain-specific forecasting principles
- Define constraints (off-limits sources, ethical boundaries)

See [writing-a-vision.md](writing-a-vision.md) for detailed guidance.

## Step 4: Customise your methods

Edit `domains/your-domain-name/methods.md`:
- The template includes five general-purpose methods — keep, modify, or remove them
- Add any domain-specific methods (e.g. for sports: Elo ratings; for politics: poll aggregation; for TV: trailer analysis)
- Don't overthink this — the whole point is that the agent will figure out what works through evidence

## Step 5: Seed your ledger

Edit `domains/your-domain-name/ledger.md`:
- Add 5-10 initial predictions
- Span different time horizons and confidence levels
- Include at least one contrarian bet
- Write clear resolution criteria

See [writing-good-questions.md](writing-good-questions.md) for guidance.

## Step 6: Set up the loop

The agent needs a scheduled trigger. Pick one:

### Option A: Claude Cowork (recommended for personal use)
See [cowork-setup.md](cowork-setup.md) for a ready-made scheduled task prompt.

### Option B: Cron + LLM CLI
Run the cycle prompt with any LLM CLI tool on a cron schedule. The cycle prompt template is in [cycle-prompt.md](cycle-prompt.md).

### Option C: GitHub Actions
Create a workflow that triggers on a schedule and calls an LLM API with the cycle prompt. Pass the four files as context.

### Option D: Manual
Just run the cycle yourself whenever you want. Copy the cycle prompt, paste it along with the four files, review the output, and update the files.

## Step 7: Run and review

After the first few cycles:
- Check `learnings.md` — is the agent noticing useful patterns?
- Check the running Brier average — is it trending down?
- Check `methods.md` — are method rankings starting to differentiate?
- Check for obvious biases — is the agent systematically overconfident? Anchoring on early predictions?

Don't adjust the system for at least 3-5 cycles. Let the baseline establish before tweaking.
