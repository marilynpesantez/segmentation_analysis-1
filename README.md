# Background
This project applies customer segmentation to the new-car market using survey responses in car_data.csv. Each row marks a unique respondent with:
- Ideal_price: Intended spend (in increments of $1,000)
- Q1-Q17: 1-7 Likert-scale agreement with statements about technology, quality/reliability, driving experience (ride, handling, performance), style/self-expression, and domestic/heritage/character.
- Purchase (0/1): Binary observation; equals 1 if the customer purchased a car within six months after completing the survey and equals 0 otherwise. 

The objective of this project is to **identify distinct consumer segments** from psychographic elements and willingness to pay to inform product, pricing, and marketing strategy.


# Executive Summary
Four distinct clusters emerged with clear psychographic and price-tolerance differences.

- Cluster 1 - Tech-Forward Stylists (21%): Leads on **trending style/design and self-expression (Q9-14)**, followed by moderate interest in **latest tech and the driving experience** (Q1-Q8). They also show an above-average ideal price ($40k) and place less weight on heritage/character cues (Q15-Q17).
Actions: Design and feature-led creative; couple language supporting advanced tech with sleek visuals.

- Cluster 2 - Value-First Convenience Seekers (43%): Defined by cost-sensitive buyers with a **low ideal price** ($20k) and a **lower interest in tech and driving performance** (Q1-Q8). They are also below average on style/design and self-expression (Q9-Q14), and show limited pull from heritage/character (Q15-Q17). Prioritize affordability and practicality above all else.
Actions: Base models; messaging around reliability of price and cost of ownership.

- Cluster 3 - Heritage & Character Loyalists (24%): Highest on **domestic/heritage/character** (Q15-Q17) with a high ideal price ($60k). They sit near average on style/self-expression (Q9-Q14) but lower on latest tech and driving performance (Q1-Q8). 
Actions: Emphasis on brand storytelling with authenticity cues; push limited/heritage editions; niche community/cult following content; avoid emphasis on specs.

- Cluster 4 - Performance-Reliability Realists (11%): Strongest on **latest tech, quality/reliability, and ride/handling/performance** (Q1-Q8). Ideal price sits around average ($30k), while style/self-expression (Q9-Q14) fall below average.
Actions: Feature-led marketing and proof-heavy marketing (safety, reliability, handling); pragmatic tone and language.


# Methodology
- Preprocessed the data: Standardized features (Ideal_Price + Likert) using StandardScale to equalize scales

- Determined the optimal k value:
-   Ran k-means (scikit-learn) with k=2 to k=10
-   Used elbow method in assessing (within-SS) and between/total% (explained variance) to spot boost in fit and. k=4 displayed a clear elbow and interpretable clusters
-   Table of k, total_within_SS, between/total%.
K=4 gave a strong drop in within-SS and +18.88pp explained variance over k=3

- Ran the K-means algorithm: 
- Applied the algorithm with k=4 to segment customers
- Validation: profile sanity checks; stability (re-seed/nearby k)

# Segment Profiles
Table with means in original units (Likert + $)
1-2 line names + narratives

# Insights and Recommendations
Product
Pricing
Brand Messaging
