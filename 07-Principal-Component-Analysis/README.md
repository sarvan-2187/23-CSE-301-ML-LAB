# 07-Principal-Component-Analysis

## Task 1: Why Maggie's Properties Are Not Selling
- Dataset: [07-pca-dataset-task-1.csv](07-pca-dataset-task-1.csv) (synthetic, 500 property listings)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/07-Principal-Component-Analysis/pca-task-1.ipynb)

### Solution
Each listing has 12 features: List_Price, Market_Value, Price_Premium_% (how far the asking price is above market value), Area_sqft, Bedrooms, Bathrooms, Age_Years, Condition_Score, Crime_Rate, School_Rating, Distance_to_City_km and Listing_Photos. It also records Days_on_Market, and Unsold_6_Months = 1 when a property has been listed for more than 180 days (134 of the 500 properties). PCA is applied to the standardised features, and 4 components explain 81.8% of the variance. The loadings show what each component represents, and each component is then compared between sold and unsold properties:

| Component | Driven by | Correlation with days on market |
|---|---|---|
| PC1 | Market value, list price, area (size) | −0.06 |
| PC2 | Crime rate, distance to city, school rating (location) | +0.29 |
| PC3 | Age, condition score (condition) | +0.41 |
| PC4 | Price premium, listing photos (pricing) | +0.54 |

**Insights for Maggie**, in order of importance:
1. **Overpricing.** Unsold properties are listed about 14% above market value, against about 2% for sold ones.
2. **Condition and age.** Unsold properties are older and have lower condition scores.
3. **Location.** Unsold properties have higher crime rates, poorer schools and are further from the city.

Size is **not** a reason, and listings with fewer photos also sell more slowly.

## Task 2: Identifying the Principal Component
- Dataset: [07-pca-dataset-task-2.csv](07-pca-dataset-task-2.csv) (the loadings table from the exercise)
- Code Base Link: [Notebook Link](https://github.com/sarvan-2187/23CSE301-ML-LAB/blob/main/07-Principal-Component-Analysis/pca-task-2.ipynb)

### Solution
The variance explained by each component is the sum of its squared loadings: PC1 = 2.835, PC2 = 0.735 and PC3 = 0.842. **PC1 is the principal component**, and **Arts (0.985)** is the variable that contributes most to it. Variables with |loading| > 0.5 are treated as significant:

| Component | Strongest variable | Significant variables (\|loading\| > 0.5) |
|---|---|---|
| PC1 | **Arts (0.985)** | Arts, Health (0.782), Transportation (0.585), Housing (0.544), Recreation (0.520) |
| PC2 | **Health (−0.605)** | Health |
| PC3 | **Crime (0.585)** | Crime, Recreation (0.519) |

Every variable loads positively on PC1, so PC1 measures the overall quality of life and amenities of a place, driven mainly by Arts and Health. The notebook also plots the loadings and computes communalities: Arts and Health (0.998 each) are almost fully explained by the 3 PCs, while Climate and Economy load weakly on all three.
