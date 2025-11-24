# Module 2: BI Analysis Workflow

## What This Does

Turns messy CSV files into actual business reports that executives can use. The whole point is to eliminate the boring stuff - data cleaning, building models, making charts - and just get to the insights in minutes instead of hours.

I built this because I was tired of watching people spend their entire afternoon on reports that should take 5 minutes.

---

## How It Works: Zero-Code Data Analyst

Here's the deal: what normally takes 4 hours (cleaning data, running analysis, writing summaries) now takes about 5 minutes. The trick is breaking down the analysis into clear steps the AI can follow systematically.

---

## The Main Prompt

### System Instructions

```markdown
# YOU'RE A DATA ANALYST WHO AUTOMATES EVERYTHING

Your job: take raw CSV data and turn it into something a CEO would actually want to read. You need to process the data through these steps in order, and show your thinking for each one.

## The 5-Step Process

### STEP 1: Check the Data Quality
Look at what we've got:
- What are the column names and what type of data is in each?
- Any missing stuff, duplicates, or weird formatting?
- What needs to be cleaned up? (don't change the original data though)
- Give me a quick report on data quality issues

### STEP 2: Basic Analysis
Run the numbers:
- Calculate the basics: average, median, range, standard deviation
- Spot any trends, patterns, or outliers
- Figure out how different variables relate to each other
- Give me a table of key statistics

### STEP 3: Regression Analysis
Build a simple model:
- Pick the right type of regression for this data
- Calculate correlation and R² values
- Tell me which factors actually matter statistically
- Give me the equation and how well it fits

### STEP 4: Find the Weird Stuff
Look for anomalies:
- Flag anything that's more than 2 standard deviations from normal
- Mark how serious each anomaly is: CRITICAL, WARNING, or just FYI
- Explain what's weird about it
- Give me a list of all the problems

### STEP 5: Executive Summary
Wrap it up:
- What's the story here? What actually matters?
- Give me 3-5 things we should do about it
- Flag anything that needs immediate attention
- Keep it under 250 words - executives don't read long stuff

## How to Format Your Answer

Spit it out as JSON like this (no markdown fences, just raw JSON):

{
  "analysis_metadata": {
    "dataset_name": "string",
    "rows_analyzed": "integer",
    "analysis_timestamp": "ISO 8601 datetime"
  },
  "data_quality": {
    "missing_values": "integer",
    "duplicates": "integer",
    "data_issues": ["array of strings"]
  },
  "statistical_summary": {
    "key_metrics": "object with metric: value pairs"
  },
  "regression_analysis": {
    "model_type": "string",
    "equation": "string",
    "r_squared": "float",
    "significant_predictors": ["array"]
  },
  "anomalies": [
    {
      "row_id": "integer",
      "severity": "CRITICAL|WARNING|INFORMATIONAL",
      "description": "string",
      "value": "any",
      "expected_range": "string"
    }
  ],
  "executive_summary": "string",
  "recommendations": ["array of 3-5 things to actually do"]
}
```

---

## How to Use It

```markdown
# WHAT YOU'RE ANALYZING

**Dataset Name:** Q4_Sales_Performance_2024
**What You're Trying to Figure Out:** Why did EMEA revenue drop 15%?
**Key Things to Look At:** revenue, customer_acquisition_cost, churn_rate

# THE DATA

[Paste your CSV here - needs headers and at least 20 rows so there's enough to analyze]

# SPECIFIC STUFF TO CHECK

- Focus on: [whatever metrics or relationships matter most]
- Flag it if: [your threshold, like "revenue drops more than 30% month-over-month"]
- Prioritize recommendations for: [specific department or area]

# RUN THE FULL ANALYSIS
```

---

## Advanced Stuff

### Handling Big Datasets

If your CSV is huge (like 50,000+ rows), you can't feed it all at once. Here's how to handle it:

```markdown
## PROCESS IN CHUNKS

Break this into pieces of 10,000 rows each. For each chunk:
1. Run steps 1-4
2. Save the results as JSON
3. Once you've done all chunks, combine everything and write the final summary

This is chunk [X of Y]
Results from last chunk: [paste JSON from previous batch]
```

### Industry-Specific Add-Ons

You can customize this for different types of analysis:

**If you're doing marketing analytics:**
```markdown
Also calculate these:
- Customer Lifetime Value (CLV)
- Conversion rates by channel
- Marketing ROI per campaign
- Attribution model results
```

**If you're doing financial analysis:**
```markdown
Also check for these red flags:
- Benford's Law violations (fraud indicator)
- Weird transaction patterns
- Budget variance over 15%
- Cash flow problems
```

### Chart Recommendations

```markdown
## SUGGEST VISUALIZATIONS

Based on what you found, tell me what charts to make:

For trends: Line chart of [metric] over time
For comparisons: Bar chart of [categories] by [metric]
For distributions: Histogram of [variable] with normal curve
For correlations: Scatter plot of [X] vs [Y] with regression line

Format as JSON:
{
  "chart_type": "string",
  "x_axis": "string",
  "y_axis": "string",
  "title": "string",
  "data_series": ["array"]
}
```

---

## Common Problems & Fixes

### Problem 1: AI Talks Instead of Giving JSON

**Fix it like this:**
```markdown
IMPORTANT: Only output JSON. Nothing else. No explanations before or after. No markdown fences. Just the raw JSON object.

If you need to explain something, put it in a "notes" field inside the JSON.
```

### Problem 2: Math Isn't Exact

**Fix it like this:**
```markdown
Show your work for calculations:
- Tell me what formula you used
- Show the steps
- Round to 2 decimal places
- Include confidence intervals if relevant
```

### Problem 3: Anomaly Detection Too Sensitive or Not Enough

**Fix it like this:**
```markdown
Adjust the sensitivity:
- First calculate the baseline on all the data
- Set the threshold at [X] standard deviations (you pick)
- Grade severity by how far off it is:
  - CRITICAL: more than 3 std dev
  - WARNING: 2-3 std dev
  - INFORMATIONAL: 1.5-2 std dev
```

---

## Real Example

### What You'd Actually Input

```markdown
# WHAT YOU'RE ANALYZING
Dataset: Q4_2024_Regional_Sales
Goal: Figure out why EMEA revenue dropped 15%
Key metrics: revenue, sales_cycle_days, deal_size, win_rate

# THE DATA
region,month,revenue,deals_closed,sales_cycle_days,deal_size,win_rate
EMEA,Oct,450000,23,45,19565,0.34
EMEA,Nov,390000,19,52,20526,0.29
EMEA,Dec,382000,18,58,21222,0.27
AMER,Oct,780000,45,38,17333,0.48
AMER,Nov,810000,48,36,16875,0.51
[... more rows ...]

# RUN THE ANALYSIS
```

### What You'd Get Back

```json
{
  "analysis_metadata": {
    "dataset_name": "Q4_2024_Regional_Sales",
    "rows_analyzed": 24,
    "analysis_timestamp": "2024-12-15T14:30:00Z"
  },
  "data_quality": {
    "missing_values": 0,
    "duplicates": 0,
    "data_issues": ["EMEA sales cycles getting longer over time"]
  },
  "statistical_summary": {
    "key_metrics": {
      "avg_revenue_emea": 407333,
      "avg_revenue_amer": 795000,
      "avg_sales_cycle_emea": 51.7,
      "avg_sales_cycle_amer": 37.0,
      "revenue_decline_emea_pct": -15.1
    }
  },
  "regression_analysis": {
    "model_type": "Multiple Linear Regression",
    "equation": "revenue = 500000 - (3500 * sales_cycle_days) + (850 * deals_closed)",
    "r_squared": 0.87,
    "significant_predictors": ["sales_cycle_days", "deals_closed", "win_rate"]
  },
  "anomalies": [
    {
      "row_id": 3,
      "severity": "CRITICAL",
      "description": "EMEA sales cycle jumped 29% from Oct to Dec",
      "value": 58,
      "expected_range": "35-45 days"
    },
    {
      "row_id": 3,
      "severity": "WARNING",
      "description": "EMEA win rate dropped to 0.27 (below 0.30 threshold)",
      "value": 0.27,
      "expected_range": "0.30-0.50"
    }
  ],
  "executive_summary": "EMEA revenue dropped 15% in Q4 (from $450K to $382K). Main culprit: sales cycles got 29% longer (now 58 days) and win rates tanked 21% (down to 27%). The regression shows sales cycle length is killing us (R²=0.87). Meanwhile AMER is doing great with 4% growth. Bottom line: EMEA needs a sales process overhaul and probably has competitive issues.",
  "recommendations": [
    "Launch a sales acceleration program in EMEA - target cutting sales cycles by 20%",
    "Do a competitive analysis for EMEA - that win rate drop screams competitive pressure",
    "Maybe borrow some top performers from AMER to help stabilize EMEA temporarily",
    "Set up an alert system - any deal past 50 days gets flagged for management review",
    "Look into why deal sizes went up 9% - bigger deals = longer cycles but might mean better margins"
  ]
}
```

---

## Connecting to Other Tools

### Getting it into Excel or Sheets

Once you have the JSON:
1. Stats go into a "Summary" sheet
2. Anomalies go into "Issues" sheet (color-code by severity - red for critical, yellow for warnings)
3. Recommendations go into "Action Items" sheet
4. Add a note about where the data came from and when you ran it

### API Setup (If You're Building This Into a System)

```markdown
POST /api/analyze-dataset
Content-Type: application/json

{
  "dataset": [your CSV as JSON],
  "analysis_type": "full_bi_pipeline",
  "config": {
    "anomaly_threshold": 2.0,
    "focus_metrics": ["revenue", "churn_rate"]
  }
}

You get back: JSON in the format above
```

---

## Time Comparison

**Doing it manually:**
- Clean the data: 45-60 mins
- Run statistics: 60-90 mins
- Build regression model: 30-45 mins
- Write the report: 45-60 mins
- **Total: 3-4 hours minimum**

**With this system:**
- Everything: 3-5 minutes
- **You save: 90%+ of your time**

**Quality check:**
- Math accuracy: Same as manual (if you make the AI show its work)
- Finding anomalies: Actually more consistent - no human brain getting tired
- Report quality: Way more consistent, way faster

---

## Test It Before You Use It

Make sure this works by testing:
- [ ] Dataset with missing values
- [ ] Big dataset (10,000+ rows)
- [ ] Check the JSON actually validates
- [ ] Verify the math is correct
- [ ] Try edge cases for anomaly detection
- [ ] Make sure summary stays under 250 words
- [ ] Test with your industry's specific metrics

---

## What to Do Next

1. Save this as `bi_analysis_workflow.md` in your `/Module-02-BI-Analysis/` folder
2. Test it with a real CSV
3. Document what worked and what didn't in `test_results.md`
4. Tweak the thresholds for your specific use case

---

## Related Stuff

- **Module 1:** How to force JSON outputs (you need this first)
- **Module 3:** Chain-of-thought prompting (goes deeper on the step-by-step thinking)
- **Module 7:** Multimodal processing (if you want to analyze images too)

---

## What This Proves

When recruiters look at this, they see you can:
- Build complex workflows that actually work
- Force AIs to give structured outputs
- Handle messy real-world data
- Generate insights that drive decisions
- Cut manual work by 90%

**For job applications:** This shows you built something that saves companies real money by automating expensive manual work.
