# Capstone Proect - Swire Coca-cola

##  Business Problem and Objective

Swire Coca-Cola United States (SCCU) aims to enhance logistics efficiency by transitioning low-volume customers to an Alternate Route to Market (ARTM). 
Currently, customers selling below an annual threshold of 400 gallons are assigned to ARTM instead of the DDR(direct delivery route). However, SCCU seeks to determine the optimal volume threshold that maximizes operational efficiency and revenue.

**Analysis will meet these missions:**

- Identifying which customers should be included in ARTM versus DDR.
- Determining the optimal volume threshold to improve logistical efficiency.

This analysis identifies strategies to increase "growth-ready" customers (those transitioning from <300 to ≥300 annual gallons) while maximizing net revenue. Key insights derived from logistic regression and XGBoost models (AUC: 0.79-0.89) inform actionable recommendations
## Key Findings

### Revenue Impact of Threshold Adjustment
| Metric                | 300-Gallon Threshold | 400-Gallon Threshold | Difference    |
|-----------------------|----------------------|----------------------|---------------|
| Net Annual Revenue    | **+$26,476.83**      | Baseline             | +$5/unit profit|

**Implementation Insight:** Lowering threshold to 300 gallons captures 34% more growth-ready customers with sustainable margins.

## Strategic Recommendations

### 1. Target "Mid-Volume" Customers
**Focus Segment:** 300-449 gallon/year customers  
**Growth Potential:** 22% higher conversion rate than 450+ gallon cohort  
**Tactics:**
- Personalized replenishment plans via MY_COKE360 portal
- Dynamic discounting for incremental volume commitments

### 2. Optimize Partnership Channels
**High-Impact Channels:**

- Sales Rep Outreach : 38% conversion lift with dedicated account managers
- EDI Integration    : 27% faster order fulfillment for chain stores
- MY_COKE360         : 41% customer retention in pilot markets

### 3. Geographic Focus
**High-Priority States:**
  - priority_states:  MA, KS, KY, MD
  -  62% of high-density customers



