# Writing Good Forecasting Questions

The quality of your predictions depends on the quality of your questions. Poorly written questions produce ambiguous outcomes that can't be scored cleanly.

## The five rules

### 1. Concrete
Bad: "Will things get worse in the Middle East?"
Good: "Will the UN Security Council pass a new resolution on Syria before 1 July 2026?"

### 2. Falsifiable
Bad: "The economy will probably be fine"
Good: "UK GDP growth for Q2 2026 will be above 0.5%"

### 3. Time-bound
Bad: "Apple will release AR glasses"
Good: "Apple will announce an AR glasses product at WWDC 2026 or earlier"

### 4. Binary or clearly gradable
Ideally yes/no. If you need a range, define the buckets upfront.
Bad: "How well will the film do?"
Good: "The film will gross over $500M worldwide in its first 30 days"

### 5. Independent
Avoid predictions that are subsets of each other. "Team X will win the league" and "Team X will finish in the top 3" aren't independent — if the first is true, the second is automatically true. Pick one.

## Confidence calibration

The hardest part isn't making predictions — it's setting confidence levels honestly.

- **50-55%:** Genuine coin flip. You have no real edge.
- **60-70%:** You lean one way but wouldn't be surprised by the other outcome.
- **75-85%:** You're fairly confident. You'd need strong counter-evidence to change your mind.
- **90%+:** Near-certain. Reserve this for things where you'd be genuinely shocked to be wrong.

A common beginner mistake is clustering predictions around 70-80%. If all your predictions are at similar confidence levels, you're not thinking hard enough about what you actually know vs. don't know.

## Seeding questions for a new domain

When starting a new forecasting domain, aim for 5-10 seed questions that:
- Span different time horizons (some resolve soon, some later)
- Span different confidence levels (some easy, some hard)
- Cover different aspects of the domain
- Include at least one contrarian prediction (something you think most people would get wrong)

The seed questions set the tone for the whole forecasting effort. They're also the first data points for evaluating your methods.

## Resolution criteria

For each prediction, be clear about what counts as "resolved." Ideally write this when you make the prediction, not when you're scoring it.

Good resolution criteria:
- "Resolved YES if [specific source] reports [specific thing] by [date]"
- "Resolved NO if [date] passes without [specific thing] happening"
- "Resolved AMBIGUOUS if [edge case] — score as 0.5"

Defining resolution criteria upfront prevents motivated reasoning when scoring.
