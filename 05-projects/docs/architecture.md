# Proposed System Architecture 

<img src='img/system_architecture.png' alt='Proposed System Architecture' width=500>
<p><strong>Proposed System Architecture<strong></p>

## Algorithms: What are we actually implementing?

| Problem | Algorithm / Technique | Evaluation |
| --- | --- | --- |
| Product associations | Apriori | Support, confidence, lift |
| Product associations | FP-Growth | Runtime, number and quality of rules |
| Demand prediction | Random Forest / XGBoost | MAE, RMSE |
| Price elasticity | Log-log regression | Elasticity coefficient, statistical significance |
| Product matching | TF-IDF / cosine similarity | Precision, recall |
| Pricing optimisation | Constrained optimisation | Revenue, margin, stock movement |

One important distinction: Apriori and FP-Growth are association rule mining algorithms, not predictive models in the traditional supervised-learning sense and demand forecasting and pricing optimisation should be evaluated separately.


## Implementation: How do we build it?

```bash 
Phase 1 – Data acquisition and exploration
- Identify and acquire supermarket transaction data.
- Inspect the dataset structure.
- Perform exploratory data analysis.
- Identify missing values, duplicates and outliers.

Phase 2 – Market Basket Analysis
- Implement Apriori.
- Implement FP-Growth.
- Compare algorithm performance.
- Generate and rank association rules.

Phase 3 – Product Placement
- Convert association rules into product relationships.
- Rank product pairings.
- Generate placement recommendations.
- Visualise product relationships as a network graph.

Phase 4 – Demand and Pricing Intelligence
- Analyse historical prices and sales.
- Estimate price elasticity.
- Develop demand forecasting models.
- Simulate pricing scenarios.

Phase 5 – Extended Modules
- Develop product matching.
- Introduce KVI identification.
- Integrate competitor pricing.
- Explore omnichannel pricing.

Phase 6 – Integration and Evaluation
- Develop the dashboard.
- Integrate analytical outputs.
- Evaluate recommendations against baseline strategies.
- Present measurable business outcomes.
```

### A. Product relationships as a network
<img src='img/product_relationship_network.png' alt='' width='600'>

This allows us to explore:

- Which products have the strongest relationships?

- Which products connect multiple categories?

- Which products have the highest number of associations?

- Which products could become strategic promotional anchors?


### B. Pricing simulation

Simulate different pricing scenarios. in CHF

| Scenario | Price | Estimated Units Sold | Revenue |
| --- | --- | --- | --- |
| Current |  100 | 500 |  50,000 |
| Scenario A |  95 | 540 |  51,300 |
| Scenario B |  105 | 460 |  48,300 |


### C. Business impact evaluation

The system should not simply produce recommendations. It should establish whether those recommendations are useful.

Potential KPIs:

- Average transaction value.

- Units per transaction.

- Cross-selling conversion.

- Revenue per product.

- Gross profit margin.

- Forecasting error.

- Inventory turnover.

- Pricing competitiveness.

Product placement should distinguish between complementary products and products that must be physically adjacent. Customers buying two products together does not automatically mean they should share a shelf. Shelf capacity, category rules, product handling, customer flow and merchandising constraints must also be considered.

Likewise, dynamic pricing should include price floors, price ceilings, margin requirements and fairness constraints. Recommendations should initially be advisory rather than automatically changing supermarket prices.

## Final positioning

An integrated, data-driven retail decision-support system that combines customer purchasing analytics, product association mining, demand forecasting and pricing optimisation to improve supermarket merchandising and commercial performance.





