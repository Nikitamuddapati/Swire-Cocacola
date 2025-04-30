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

**1. Implement Logistic Regression (AUC:0.79) and XGboost models (AUC:0.89)** to increase "growth-ready" customers while maximizing net revenue, and optimizing costs.

**2. Implement a 300 Gallons Threshold:** captures 34% more growth-ready customers and increases revenue by $26,476.83, compared to initial threshold of 400 gallons.


| Metric                | 300-Gallon Threshold | 400-Gallon Threshold | Difference    |
|-----------------------|----------------------|----------------------|---------------|
| Net Annual Revenue    | **+$26,476.83**      | Baseline             | +$5/unit profit|


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


## Business Value of Solution

**1. Data-Backed Strategic Planning:** Sensitivity analysis and scenario testing support leadership decisions on volume thresholds and customer prioritization, helping allocate resources where the ROI is highest.

**2. Increased Revenue Through Targeted Growth**: By identifying "growth-ready" customers with predictive modeling (XGBoost), Swire can proactively target mid-volume customers (e.g., 300–449 gallons) who are most likely to grow with tailored campaigns—potentially boosting annual revenue significantly.

**3. Optimized Delivery Cost Allocation:** The analysis of low-cost, growth-ready customers enables Swire to prioritize efficient accounts that yield high return per delivery dollar spent, maximizing profitability.

**4. Smarter Customer Segmentation & Retention:** Customer insights (such as order size, digital engagement, CO2 purchases, trade channel) help Swire tailor retention strategies and improve the customer experience for specific segments like Local Market Partners or Dining channels.


## Contribution

- **Data Preparation & EDA**: Performed data transformation, merged datasets, and conducted in-depth exploratory data analysis  to understand customer patterns, order behaviours, and volume distributions.

- **Sensitivity Analysis:** Used a custom function approach to identify the optimal threshold for all customers that minimizes the total delivery costs across both years to approximately $47 million, while also retaining 3,380 more high-potential customers. This would help Swire increase the total number of high-potential customers to 9,841, striking a better balance between cost efficiency and growth potential.

- **Delivery Cost Metrics:** Extracted annual delivery costs and computed cost statistics for 2023 and 2024 per customer by cases and gallons, identifying cost drivers and yearly shifts in operational efficiency.

- **Local Market Partner Analysis:** Performed targeted analysis on group2 customers - Local Market Partners who exclusively buy fountain drinks, calculating annual purchase, volume, and cost trends across 2023 and 2024.

- **Modelling:** Built multiple blackbox and whitebox models(Logistic regression, XGboost, and Random Forest) using GridSearchCV for hyper parameter tuning  to predict growth-ready customers and evaluated models using ROC-AUC, F1 Score, and classification reports.

- **Growth-ready customer characteristics:** Extracted key characteristics of growth-readiness including transaction frequency, order size, delivery type, and trade channel.

  - Identified a segment of **growth-ready customers with lowest delivery costs**, revealing scalable growth opportunities.

  - Conducted feature importance analysis to determine the most influential variables in customer growth prediction (e.g., ordering platform usage, order volume, channel type).

- **Interactive Visualizations:** Designed interactive and real-time Tableau plots to visualize customer volume trends, delivery cost distributions, and high-potential customer segments across states and trade channels.

- **Final Presentation:** Delivered actionable insights and presented findings to stakeholders with clear business recommendations summarizing growth + low-cost trends, model results, and ROI strategies.


## Challenges Faced

- **Mapping delivery costs** to customer volume was complex due to tiered ranges, requiring range-based conditional joins to correctly assign each customer’s annual volume to match appropriate volume tier. This was handled by using between() in R (and later adapted to Python using merge + filtering) and calculating cost per customer using conditional logic for both case and gallon.

- **Determining the optimal threshold** for identifying growth-ready customers required balancing both minimimal delivery costs and maximum number of high potential customers.

- **Distinguishing between feature importance and actual customer characteristics** required building comparative feature means to identify true growth-ready vs non growth-ready traits beyond what the model relies on.

- **Integrating and aligning diverse analytical outputs** from different team members into a unified, final deliverable.

- **Segmenting customers** accurately by clustering using ZIP code-level geographic data.

- **Class imbalance** in the target variable (only 4% growth-ready) made modeling difficult, which was addressed using stratified sampling, ROC-AUC evaluation, and boosting techniques.


## Learnings

**1. Bridging Business and Data:** I learned how to interpret analytical results in terms of business impact, connecting data insights to strategic decisions that drive growth and cost optimization.

**2. Handling Complex Joins & Volume Ranges:** Working with delivery cost tables that relied on volume range conditions enhanced my skills in conditional merging and applying logic-driven joins.

**3. Sensitivity Analysis for Strategy:** I learned to apply sensitivity analysis to uncover operational levers like threshold tuning, which can optimize both growth potential and cost efficiency.

**4. Communicating Insights Visually:** Creating presentation visuals and dashboards helped me better understand what the data truly conveys in technical terms, while also improving my ability to clearly communicate insights to both technical and business audiences.

**5. Team Work:** I strengthened my collaboration skills by solving analytical challenges together and synthesizing our findings into a recommendation. I also learned new approaches and perspectives from their ideas and modeling techniques.



