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

**1.Implement Logistic Regression (AUC:0.79) and XGboost models (AUC: 0.89)** to increase "growth-ready" customers while maximizing net revenue, and optimize costs.

| Metric                | 300-Gallon Threshold | 400-Gallon Threshold | Difference    |
|-----------------------|----------------------|----------------------|---------------|
| Net Annual Revenue    | **+$26,476.83**      | Baseline             | +$5/unit profit|


**2. Implement a 300 Gallons Threshold:** captures 34% more growth-ready customers and increases revenue by $26,476.83, compared to initial threshold of 400 gallons.

**3. Target "Mid-Volume" Customers**

Focus Segment: 300-449 gallon/year customers  
Growth Potential: 22% higher conversion rate than 450+ gallon cohort  

Tactics:
- Personalized replenishment plans via MY_COKE360 and EDI digital ordering platforms
- Dynamic discounting for incremental volume commitments

**4. Optimize Partnership Channels**

High-Impact Channels:
- Sales Rep Outreach : 38% conversion lift with dedicated account managers
- EDI Integration    : 27% faster order fulfillment for chain stores
- MY_COKE360         : 41% customer retention in pilot markets

**5. Geographic Focus**

High-Priority States:
  - priority_states:  MA, KS, KY, MD
  -  62% of high-density customers

## My Contribution

**Data Preparation & EDA**: Performed data transformation, merged datasets, and conducted in-depth exploratory data analysis  to understand customer segmentation patterns, order behaviours, and volume distributions.

**Sensitivity Analysis:** Used a custom function approach to identify the optimal threshold for all customers that minimizes the total delivery costs across both years to approximately $47 million, while also retaining 3,380 more high-potential customers. This would help Swire increase the total number of high-potential customers to 9,841, striking a better balance between cost efficiency and growth potential.

**Delivery Cost Metrics:** Extracted annual delivery costs and computed cost statistics for 2023 and 2024 per customer by cases and gallons, identifying cost drivers and yearly shifts in operational efficiency.

**Local Market Partner Analysis:** Performed targeted analysis on group2 customers - Local Market Partners who exclusively buy fountain drinks, calculating annual purchase, volume, and cost trends across 2023 and 2024.

**Modelling:** Built multiple blackbox and whitebox models(Logistic regression, XGboost, and Random Forest) using GridSearchCV for hyper parameter tuning  to predict growth-ready customers and evaluated models using ROC-AUC, F1 Score, and classification reports.

**Growth-ready customer characteristics:** Extracted key characteristics of growth-readiness including transaction frequency, order size, delivery type, and trade channel.

•	Identified a segment of **growth-ready customers with lowest delivery costs**, revealing scalable growth opportunities.

•	Conducted feature importance analysis to determine the most influential variables in customer growth prediction (e.g., ordering platform usage, order volume, channel type).

**Interactive Dashboards:** Designed interactive Tableau dashboards to visualize customer volume trends, delivery cost distributions, and high-potential customer segments across states and trade channels.

**Final Presentation:** Delivered actionable insights and presented findings to stakeholders with clear business recommendations summarizing growth + low-cost trends, model results, and ROI strategies.

## Challenges Faced

**1. Mapping delivery costs** to customer volume was complex due to tiered ranges, requiring range-based conditional joins to correctly assign each customer’s annual volume to match appropriate volume tier. This was handled by using between() in R (and later adapted to Python using merge + filtering) and calculating cost per customer using conditional logic for both case and gallon.

**2. Determining the optimal threshold** for identifying growth-ready customers required balancing minimimal delivery costs while maximize the number of high potential customers.

**3. Class imbalance** in the target variable (only 4% growth-ready) made modeling difficult, which was addressed using stratified sampling, ROC-AUC evaluation, and boosting techniques.

**4. Distinguishing between feature importance and actual customer characteristics** required building comparative feature means to identify true growth-ready vs non growth-ready traits beyond what the model relies on.

