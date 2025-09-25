# 🎯 Brand and Product Review Sentiment & Emotion Analysis

## 💡 Executive Summary

This project addresses the challenge of monitoring **brand reputation** and **customer sentiment** at scale using social media data (tweets). We applied both **lexicon-based** scoring and **machine learning classification** (using TF-IDF + XGBoost) to a benchmark dataset of $\approx 9,000$ tweets. The analysis successfully compared the sentiment between major competitors (Apple vs. Google) and built a predictive model to classify emotions. While the ML model achieved an accuracy of $\approx 67\%$, it highlighted the limitations of traditional models in handling class imbalance and nuance, paving the way for advanced NLP exploration.

---

## 🧐 Business Problem

In the digital age, customer feedback on social media is a critical strategic asset. Manual analysis is impossible due to the sheer volume of data. This project solves the scale problem by demonstrating an automated pipeline to:
1.  **Monitor Brand Mentions:** Systematically extract and aggregate mentions of products and brands.
2.  **Quantify Sentiment:** Assign objective sentiment and emotion labels to unstructured text.
3.  **Inform Strategy:** Provide real-time, actionable insights to guide product development, marketing campaigns, and reputation management.

---

## 🛠️ Requirements

To replicate this analysis, you need R and the following packages:

### Prerequisites
* **R** (Version 3.6+)
* **RStudio** (Recommended IDE)

### R Packages
The following packages are used for data handling, text processing, modeling, and visualization:

```r
required <- c("tidyverse", "tidytext", "caret", "glmnet", "Matrix",
              "ggplot2", "scales", "doParallel", "xgboost", "MLmetrics")
# The required packages can be installed using:
# install.packages(required)
```

## Installation and Setup

### 1. Clone the Repository
Clone the project repository to your local machine:

```bash
git clone [https://github.com/IshwaryaKeerthivasan/Sentiment-Analysis.git](https://github.com/IshwaryaKeerthivasan/Sentiment-Analysis.git)
cd Sentiment-Analysis
```
## 2. Data
The analysis uses the "Brands and Product Emotions" dataset from Crowdflower / Figure Eight.

* **Source:** [data.world/crowdflower/brands-and-product-emotions](https://data.world/crowdflower/brands-and-product-emotions)
* **Action:** Download the file (`Brand and product review tweet.csv`) and place it in the root directory of this project, or update the file path in the R script.

---

## 3. Run the Analysis
Execute the main R script to run the data preparation, lexicon analysis, and machine learning model training:

```bash
# This assumes the analysis steps are in an R script or R Markdown file.
# You may need to adjust the filename based on your project structure.
Rscript -e 'rmarkdown::render("Brand_and_product_Reviews.Rmd")'
```
## ✨ Features

* **Data Preparation:** Cleaning, tokenization, and brand consolidation (**Apple**, **Google**).
* **Exploratory Analysis:** Visualization of top-mentioned brands and their emotion breakdowns.
* **Lexicon-Based Sentiment:** Used the **Bing lexicon** for quick and interpretable sentiment scoring.
* **Machine Learning Pipeline:** Developed a classification pipeline using **TF-IDF** feature engineering.
* **Predictive Modeling:** Trained and evaluated **XGBoost** for multi-class emotion classification (Positive, Negative, No emotion).
* **Competitive Comparison:** Direct comparison of average sentiment scores between Apple and Google.

---

## 🧠 Methodology

1.  **Data Cleaning:** Handled missing values, tokenized tweet text, and removed stop words.
2.  **Feature Engineering:** Calculated **TF-IDF** scores for machine learning inputs.
3.  **Lexicon Scoring:** Calculated a sentiment score for each tweet ($\text{positive words} - \text{negative words}$).
4.  **Modeling:** Employed a **70/30 train-test split** and trained **XGBoost** with a softprob objective for multi-class prediction.
5.  **Evaluation:** Models were compared using **Accuracy**, **Kappa**, and class-specific **F1-Scores** (to measure sensitivity to minority classes).

---

## 💻 Skills

* **Programming:** **R**
* **Data Manipulation:** `tidyverse`
* **NLP/Text Mining:** `tidytext`, Tokenization, Stopword removal, **TF-IDF**
* **Machine Learning:** **XGBoost** (Primary model), Logistic Regression, Naive Bayes, SVM (as benchmark models)
* **Model Evaluation:** `caret` (Confusion Matrices, Kappa, Accuracy)
* **Visualization:** `ggplot2`

---

## 📈 Results & Business Recommendation

### Key Insights
* **Competitive Perception:** Apple and Google were the most mentioned brands, showing distinct, quantifiable sentiment profiles.
* **XGBoost Performance:** The final multi-class emotion classifier achieved an overall **accuracy of $\approx 67\%$**.
* **Model Limitations:** **Class imbalance** significantly impacted the model's ability to accurately detect "**Negative emotion**" (low F1-Score for this class), which is a crucial business metric.

### Business Recommendation
The analysis provides **actionable intelligence** to:
1.  **Benchmark Competitors:** Use sentiment scores to track relative market perception against rivals.
2.  **Proactive Reputation Management:** Flag tweets predicted as "**Negative emotion**" for immediate response and issue resolution.
3.  **Guide Product Teams:** Summarize common issues derived from negative tweets to prioritize feature improvements and bug fixes, thereby improving customer satisfaction.

---

## ⏭️ Next Steps

To move the project to a production-ready state and achieve better predictive performance, the following steps are recommended:

* **Transformer Models (BERT):** Fine-tune a pre-trained **BERT** model for state-of-the-art emotion classification, leveraging its superior contextual understanding of language and slang.
* **Bias Mitigation:** Implement oversampling (e.g., **SMOTE**) or utilize class weighting during training to improve the model's sensitivity to the minority "**Negative emotion**" class.
* **Deployment:** Build an interactive **R Shiny dashboard** for real-time visualization of incoming sentiment data and key metrics.

---

## ✍️ Author & Source

* **Author:** **Ishwarya keerthivasan**
* **Dataset Acknowledgment:** Crowdflower / Figure Eight
* **Project Link:** [[(https://github.com/IshwaryaKeerthivasan/Sentiment-Analysis)](https://github.com/IshwaryaKeerthivasan/Sentiment-Analysis)]
