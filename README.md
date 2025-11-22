
# Association Rule Mining on Online Retail Dataset
### Aime-232

---

## 1. Project Overview

This project explores **association rule mining**, a data mining technique used to discover interesting relationships between items in transactional datasets.  
By identifying patterns of products bought together, businesses can gain insights into **customer buying behavior**, guiding strategies for **product bundling, cross-selling, and recommendation systems**.

The analysis is performed on the **Online Retail Dataset (UK)**, containing over **500,000 transactions** from a UK-based online retail store.

The full analysis is available in Google Colab:
[Open in Colab](https://colab.research.google.com/drive/1CDdirI1wwc3TAbX_DcWpOkhcFczElQhE?usp=sharing)

---

## 2. Dataset Description

**Dataset Fields:**

- `InvoiceNo`: Invoice number for each transaction  
- `StockCode`: Product code  
- `Description`: Product description  
- `Quantity`: Number of units purchased  
- `InvoiceDate`: Date and time of the transaction  
- `UnitPrice`: Price per unit  
- `CustomerID`: Unique identifier for each customer  
- `Country`: Customer country  

**Enhancement:** A **ProductCategory** column was added using **NLP and clustering** to group similar products, enabling more generalized association analysis.

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail)

---

## 3. Key Steps & Libraries Used

**Data Preparation:**  
- Removed duplicates and missing values  
- Filtered transactions with positive quantities  
- Converted data into **basket format** for analysis  
- Added **ProductCategory** column  

**Frequent Itemset Mining:**  
- Algorithm: **Apriori**  
- Minimum support thresholds: 0.02, 0.05 (item-level), 0.05, 0.1 (category-level)  

**Association Rules Generation:**  
- Metrics used: **support, confidence, lift**  
- Top rules identified for actionable insights  


---

## 4. Frequent Itemset Mining

### 4.1 Item-Level (min_support = 0.02)

| Support  | Itemset                            |
| -------- | ---------------------------------- |
| 0.106357 | WHITE HANGING HEART T-LIGHT HOLDER |
| 0.091895 | REGENCY CAKESTAND 3 TIER           |
| 0.086337 | JUMBO BAG RED RETROSPOT            |
| 0.074412 | PARTY BUNTING                      |
| 0.074196 | ASSORTED COLOUR BIRD ORNAMENT      |
| 0.069501 | LUNCH BAG RED RETROSPOT            |
| 0.061839 | SET OF 3 CAKE TINS PANTRY DESIGN   |
| 0.059303 | POSTAGE                            |
| 0.056767 | LUNCH BAG BLACK SKULL.             |
| 0.055526 | PACK OF 72 RETROSPOT CAKE CASES    |

**Interpretation:**

* The most frequently purchased item is the **WHITE HANGING HEART T-LIGHT HOLDER** (~10% of transactions).
* Items like **REGENCY CAKESTAND 3 TIER** and **JUMBO BAG RED RETROSPOT** are also highly frequent, indicating popular home and gift products.
* Small accessories and party supplies appear consistently, suggesting strong seasonal or decorative demand.

<img width="1094" height="450" alt="image" src="https://github.com/user-attachments/assets/023716fe-a77a-4f22-b60b-776336cc4023" />


---

### 4.2 Category-Level (min_support = 0.05)

| Support  | Itemset                                                    |
| -------- | ---------------------------------------------------------- |
| 0.946201 | Mugs & Home Messages                                       |
| 0.568206 | Gift Sets & DIY Craft Kits                                 |
| 0.565994 | Fashion & Personal Accessories                             |
| 0.556443 | Fashion & Personal Accessories, Mugs & Home Messages       |
| 0.554770 | Bags & Storage Accessories                                 |
| 0.547701 | Mugs & Home Messages, Gift Sets & DIY Craft Kits           |
| 0.532754 | Mugs & Home Messages, Bags & Storage Accessories           |
| 0.394075 | Fashion & Personal Accessories, Bags & Storage Accessories |
| 0.389974 | Fashion & Personal Accessories, Mugs & Home Messages       |
| 0.369739 | Fashion & Personal Accessories, Gift Sets & DIY Craft Kits |

**Interpretation:**

* Categories like **Mugs & Home Messages** dominate transactions, reflecting everyday household purchases.
* Combinations such as **Fashion & Personal Accessories with Mugs & Home Messages** indicate cross-category purchasing behavior.
* Insights at the category level can guide bundling and marketing strategies.

<img width="1094" height="450" alt="image" src="https://github.com/user-attachments/assets/fa82c8a2-bd28-417a-964d-dd61caf308cb" />

---

## 5. Association Rules

### 5.1 Top Association Rules (Category-Level)

| Antecedents                                      | Consequents                                                | Support  | Confidence | Lift  |
| ------------------------------------------------ | ---------------------------------------------------------- | -------- | ---------- | ----- |
| Gift Sets & DIY Craft Kits, Party & Celebration  | Fashion & Personal Accessories, Mugs & Home Messages       | 0.114882 | 0.746      | 1.913 |
| Mugs & Home Messages, Gift Sets & DIY Craft Kits | Fashion & Personal Accessories, Bags & Storage Accessories | 0.114882 | 0.751      | 1.907 |
| Gift Sets & DIY Craft Kits, Party & Celebration  | Fashion & Personal Accessories, Bags & Storage Accessories | 0.114936 | 0.746      | 1.894 |

**Interpretation:**

* Customers buying **Gift Sets & DIY Craft Kits** often purchase **Fashion & Personal Accessories** and **Mugs & Home Messages**, suggesting potential **cross-selling opportunities**.
* High lift values (>1.8) indicate strong positive association between these categories.
* Insights can inform **targeted promotions** and **product recommendations**.

<img width="1094" height="450" alt="image" src="https://github.com/user-attachments/assets/48c51257-a859-4850-9e87-194e17e1eff1" />

---

## 6. Key Insights

1. Home decor, party items, and fashion accessories are the most frequent purchases.
2. Cross-category patterns highlight opportunities for **bundling products** in promotions.
3. Item-level analysis identifies specific high-demand products, while category-level analysis uncovers broader purchasing trends.
4. Businesses can leverage these patterns for **inventory planning, marketing campaigns, and personalized recommendations**.

---

For questions or feedback, reach out to:
Email: aimmug200507@gmail.com



