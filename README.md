## 1. Overview
This project applies customer segmentation to the new-car market using survey responses in car_data.csv. The objective of this project is to **identify distinct consumer segments** from psychographic elements and willingness to pay to inform product, pricing, and marketing strategy.

## 2. Executive Summary
Four distinct clusters emerged with clear psychographic and price-tolerance differences.

### Segment Overview
- Cluster 1 - Tech-Forward Stylists (21%): Leads on **trending style/design and self-expression (Q9-14)**, followed by moderate interest in **latest tech and the driving experience** (Q1-Q8). They also show an above-average ideal price ($40k) and place less weight on heritage/character cues (Q15-Q17).
Actions: Design and feature-led creative; couple language supporting advanced tech with sleek visuals.
- Cluster 2 - Value-First Convenience Seekers (43%): Defined by cost-sensitive buyers with a **low ideal price** ($20k) and a **lower interest in tech and driving performance** (Q1-Q8). They are also below average on style/design and self-expression (Q9-Q14), and show limited pull from heritage/character (Q15-Q17). Prioritize affordability and practicality above all else.
Actions: Base models; messaging around reliability of price and cost of ownership.
- Cluster 3 - Heritage & Character Loyalists (11%): Highest on **domestic/heritage/character** (Q15-Q17) with a high ideal price ($60k). They sit near average on style/self-expression (Q9-Q14) but lower on latest tech and driving performance (Q1-Q8). 
Actions: Emphasis on brand storytelling with authenticity cues; push limited/heritage editions; niche community/cult following content; avoid emphasis on specs.
- Cluster 4 - Performance-Reliability Realists (24%): Strongest on **latest tech, quality/reliability, and ride/handling/performance** (Q1-Q8). Ideal price sits around average ($30k), while style/self-expression (Q9-Q14) fall below average.
Actions: Feature-led marketing and proof-heavy marketing (safety, reliability, handling); pragmatic tone and language.


## 3. Segmentation

### Variables for Clustering
- Ideal_price: Intended spend (in increments of $1,000)
-   Q1-Q17: 1-7 Likert-scale agreement with statements about technology, quality/reliability, driving experience (ride, handling, performance), style/self-expression, and domestic/heritage/character.
-   Purchase (0/1): Binary observation; equals 1 if the customer purchased a car within six months after completing the survey and equals 0 otherwise.

### Clustering Analysis in Python
**(1) Preprocess data:** Standardized features (Ideal_Price + Likert) using StandardScale to equalize scales

**(2) Determine optimal k value:**
- Ran k-means (scikit-learn) with k=2 to k=10
- Assessed fit using elbow method to spot drop in within-cluster sum of squares
- K=4 displayed a clear elbow with a strong drop in within-SS as well as a +16.027pp increase in between/total% (explained variance) from k=3. 
<p align="center">
<img width="600" height="440" alt="image" src="https://github.com/user-attachments/assets/80643398-91bb-4166-a15b-0bd80e303d83" />
</p>

**(3) Ran the K-means algorithm with k=4**
- Produced cluster centers in both standardized units and original units
- Validation: k=4 displayed interpretable cluster profiles and stability (re-seed/nearby k)

### Output
**Cluster means in standardized units (z-scores):**
<p align="center">
<img width="800" height="300" alt="image" src="https://github.com/user-attachments/assets/f7e79f3e-464d-4004-80cb-9e6297d960f8" />
</p>

**Cluster means in original units (Likert + $)**
<p align="center">
<img width="800" height="278" alt="image" src="https://github.com/user-attachments/assets/00a89130-7c97-4b62-976d-5064e4826f07" />
</p>

**Top differentiating questions**
<p align="center">
<img width="800" height="260" alt="image" src="https://github.com/user-attachments/assets/53eb9d9e-c614-40c0-9927-b9085337fce6" />
</p>


## 4. Cluster Profiles & Emplications
For each cluster, I interpreted cluster means to identify defining attributes and translated those patterns into psychographic and price tolerance profiles. I also outline actionable next steps across product, pricing, and marketing.

### Cluster 1 — Tech-Forward Stylists (21%)
Profile: Lead on trending style/design & self-expression (Q9–Q14). The car is part of personal identity, followed by a strong interest in having the latest tech and enjoying the driving experience (Q1–Q8). They also show above-average Ideal_Price [+$9.0k vs avg], and are least driven by heritage/character cues (Q15–Q17).
- Positioning & creative: Design-first storytelling with visible tech; sleek visuals, UI/UX demos, “always up to date.”
- Product & pricing: Premium trims; tech + aesthetics bundles; consider OTA/subscription features.
- Next tests: A/B “latest tech” vs “style/design” ads; measure CTR→CVR and premium-trim mix.

### Cluster 2 — Value-First Convenience Seekers (43%)
Profile: Low Ideal_Price (cost-sensitive) comes first. They show less interest in tech and driving performance (Q1–Q8) and sit below average on style/design & self-expression (Q9–Q14), with limited pull from heritage/character (Q15–Q17). Practicality and total cost dominate.
- Positioning & creative: Lead with affordability, transparent pricing/financing, warranty and fuel-economy claims; remove friction in the path to buy.
- Product & pricing: Base/entry trims, value packs, service incentives; emphasize TCO and reliability.
- Next tests: Offer-led experiments (APR, cash back) by segment; track uptake vs margin.

### Cluster 3 — Heritage & Character Loyalists (11%)
Profile: Highest on domestic/heritage/character (Q15–Q17) and premium price tolerance [+$28.9k vs avg]. They’re near average on style/self-expression (Q9–Q14) but lower on latest tech and drive/performance (Q1–Q8). Identity and provenance matter more than specs.
- Positioning & creative: Brand storytelling, craftsmanship, provenance; community/cult-following content; lean into authenticity.
- Product & pricing: Limited/heritage editions, collectible options, branded accessories, loyalty programs.
- Next tests: Story-led vs spec-led creatives; measure engagement, accessory attach, and high-margin package mix.

### Cluster 4 — Performance-Reliability Realists (24%)
Profile (what defines them): Strongest on tech + quality/reliability + ride/handling/performance (Q1–Q8). Ideal_Price is about average [≈ $29.8k], while style/self-expression (Q9–Q14) and heritage (Q15–Q17) are less influential. They value how the car drives and holds up.
- Positioning & creative: Proof-heavy messaging — safety data, reliability stats, handling/road-feel demos; pragmatic tone.
- Product & pricing: Mid→upper functional trims (performance & safety packages); extended-warranty angles.
- Next tests: “Handling/safety” vs “value/comfort” narratives; track test-drive bookings and close rate.
