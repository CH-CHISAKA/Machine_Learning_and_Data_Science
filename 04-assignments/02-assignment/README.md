# 1. Sampling: 
Goal
Understand how the sampling distribution of the sample mean changes with sample size and practice sampling in Python 

## Setup
Population: Exponential(λ = 1) with mean μ = 1 and SD σ = 1. (Optional: also try Normal(0,1).)
n = sample size within one draw (use several values, e.g., 5, 10, 50, 100).
N = number of independent repetitions for each n (use a large value, e.g., N = 10,000).

What to do (for each n)
Repeat N times: draw n independent observations from the population and compute the sample mean ?┴ˉ. (You’ll have N sample means.
Make a histogram/density of those N sample means. 

Report a small table with: n, empirical mean of sample means, empirical SD of sample means.

Write (3–5 sentences)
Describe how shape changes (if using exponential), how spread changes.

# 2. Task. 
Write plain-language pseudocode (5–10 lines) for k-fold CV to estimate a model’s performance. Imagine you already chose a model (e.g., linear regression). 

Focus on steps, not code.
Tip: Write it like a recipe. Example starters: “Load the data
Shuffle data
split into k equal parts → for fold i in 1…k: … 
”