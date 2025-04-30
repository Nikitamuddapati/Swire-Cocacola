# Capstone Project - Swire Cocacola

##  Business Problem and Objective

SCCU tries to optimize logistics by transitioning customers selling below a specific annual volume to an Alternate Route to Market (ARTM). They currently use 400 gallons volume threshold to distinguish between the direct delivery route and ARTM. However, misclassifications in the existing threshold results in missed opportunities for revenue expansion and weakened customer relationships. 
SCCU is looking for a more cost-efficient strategy for optimizing costs that drives operational efficiencies and more revenues. By leveraging advanced analytics, SCCU can ensure that high-growth customers remain 
on direct delivery routes, sustaining their full revenue potential while optimizing logistical efficiency by switching low-growth ones to ARTM. 

**Analysis will meet these missions:**

- Identifying which customers should be moved to DDR verses ARTM.
- Determining the optimal volume threshold to improve logistical efficiency.

This analysis identifies strategies to increase "growth-ready" customers (those transitioning from <300 to ≥300 annual gallons) while maximizing net revenue. Key insights derived from logistic regression and XGBoost models (AUC: 0.79 and 0.89) inform actionable recommendations.

## Business Solution and Strategic Recommendations


| Metric                | 300-Gallon Threshold | 400-Gallon Threshold | Difference    |
|-----------------------|----------------------|----------------------|---------------|
| Net Annual Revenue    | **+$26,476.83**      | Baseline             | +$5/unit profit|

**1. Implement a 300 gallons threshold:** captures 34% more growth-ready customers and increases revenue by $26,476.83, compared to initial threshold of 400 gallons.

**2. Target "Mid-Volume" Customers**

Focus Segment: 300-449 gallon/year customers  
Growth Potential: 22% higher conversion rate than 450+ gallon cohort  

Tactics:
- Personalized replenishment plans via MY_COKE360 and EDI digital ordering platforms
- Dynamic discounting for incremental volume commitments

**3. Optimize Partnership Channels**

High-Impact Channels:
- Sales Rep Outreach : 38% conversion lift with dedicated account managers
- EDI Integration    : 27% faster order fulfillment for chain stores
- MY_COKE360         : 41% customer retention in pilot markets

**4. Geographic Focus**

High-Priority States:
  - priority_states:  MA, KS, KY, MD
  -  62% of high-density customers

## My Contribution


