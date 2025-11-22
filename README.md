
# Association Rule Mining on Online Retail Dataset
### Aime-232

---

## 1. Project Overview

This project explores **association rule mining**, a key data mining technique for discovering interesting relationships between products in transactional datasets.  
By analyzing patterns of products bought together, businesses can gain insights into **customer buying behavior**, which can inform strategies for **product bundling, cross-selling, and recommendation systems**.

---

## 2. Dataset Description

* **Dataset:** [Online Retail Dataset (UK)](https://archive.ics.uci.edu/ml/datasets/Online+Retail)  
* **Description:**  
  The dataset contains over **500,000 transactions** from a UK-based online retail store. Each record includes:

  - `InvoiceNo`: Invoice number  
  - `StockCode`: Product code  
  - `Description`: Product description  
  - `Quantity`: Number of units purchased  
  - `InvoiceDate`: Date and time of the transaction  
  - `UnitPrice`: Price per unit  
  - `CustomerID`: Unique identifier for each customer  
  - `Country`: Customer country  

* **Enhancement:**  
  A **ProductCategory** column was added using **natural language processing (NLP)** and **clustering techniques** to group similar products for more meaningful category-level analysis.

---

## 3. Key Steps & Libraries Used

**Data Preparation:**  
- Removed duplicates and missing values  
- Filtered transactions with positive quantities  
- Converted data into **basket format** for association analysis  

**Frequent Itemset Mining:**  
- Algorithm: **FP-Growth**  
- Minimum support thresholds: 0.02, 0.05 (item-level); 0.05, 0.1 (category-level)  

**Association Rules Generation:**  
- Metrics: **support, confidence, lift**  
- Filtered to identify strong, actionable rules  

**Libraries Used:**  
```python
from mlxtend.frequent_patterns import fpgrowth
import plotly.express as px


---

## 4. Sample Outputs

### Frequent Itemsets (Category-Level)

| Support | Itemsets                                             |
| ------- | ---------------------------------------------------- |
| 0.946   | Mugs & Home Messages                                 |
| 0.568   | Gift Sets & DIY Craft Kits                           |
| 0.566   | Fashion & Personal Accessories                       |
| 0.556   | Fashion & Personal Accessories, Mugs & Home Messages |
| 0.555   | Bags & Storage Accessories                           |

### Top Association Rules (Category-Level)

| Antecedents                                        | Consequents                                                  | Support  | Confidence | Lift  |
| -------------------------------------------------- | ------------------------------------------------------------ | -------- | ---------- | ----- |
| (Gift Sets & DIY Craft Kits, Party & Celebration)  | (Fashion & Personal Accessories, Mugs & Home Messages)       | 0.114882 | 0.746      | 1.913 |
| (Mugs & Home Messages, Gift Sets & DIY Craft Kits) | (Fashion & Personal Accessories, Bags & Storage Accessories) | 0.114882 | 0.751      | 1.907 |

*Insert screenshots of plots here if available*

---

## 5. Interpretations

* Most purchased items are small decorative or household goods.
* Category-level rules reveal complementary products for **cross-selling and bundling**.
* Insights can inform **inventory planning, marketing campaigns, and product recommendation systems**.

---

## 6. Colab Notebook

You can explore the full analysis and code in Google Colab:
[Open in Colab](https://colab.research.google.com/drive/1CDdirI1wwc3TAbX_DcWpOkhcFczElQhE?usp=sharing)

---

