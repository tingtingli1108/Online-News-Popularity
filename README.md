# Lab 2: Online News Popularity

## 📖 Overview
This project investigates whether publishing entertainment-focused articles on **weekends** influences their popularity on **Mashable**, as measured by article **share counts**. Using the **Online News Popularity dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/332/online+news+popularity), we apply statistical modeling to assess the relationship between publication timing and article shares.

Our analysis indicates that entertainment articles published on weekends receive **~34% more shares** compared to weekdays, though the models show low predictive power overall.  

---

## 🎯 Research Question
- **X concept (independent variable):** `is_weekend` – whether an article is published on weekends.  
- **Y concept (dependent variable):** `shares` – the number of times the article is shared (log-transformed in modeling).  

**Core Question:**  
*Does publishing entertainment-focused articles on weekends increase their share counts on Mashable?*

---

## 👥 Stakeholders
- **Actors (who can change X):**
  - Content managers & editors  
  - Publishing strategists  
  - Digital marketing teams  

- **Audience (who cares about Y):**
  - Content creators & editors  
  - Website managers & SEO specialists  
  - Data analysts  
  - Advertisers & sponsors  
  - Readers & competitors of Mashable  

---

## 📊 Data
- **Source:** Online News Popularity dataset (UCI ML Repository)  
- **Period:** Jan 7, 2013 – Jan 7, 2015  
- **Size:** 39,644 articles × 61 features  
- **Unit of observation:** A single article  

**Key Features Used:**
- `is_weekend` (weekend publication indicator)  
- `shares` (dependent variable, log-transformed)  
- Content and metadata features:  
  - `n_tokens_content`, `n_tokens_title`  
  - `num_hrefs`, `num_imgs`, `num_videos`  
  - `LDA_00` … `LDA_04` (topic closeness)  
  - Article channel (e.g., lifestyle, entertainment, tech)  

---

## ⚙️ Methodology
1. **Exploratory Data Analysis (EDA)** – distribution checks, skewness analysis.  
2. **Data Transformation** – log-transformation of `shares` to reduce skewness.  
3. **Modeling** – Ordinary Least Squares (OLS) regression with multiple model variations:  
   - Base model: `log(shares) ~ is_weekend`  
   - Extended models: include text length, subjectivity, keywords, links, images, videos, etc.  
4. **Validation** – Data split into 30% exploration set and 70% confirmation set.  
5. **Assumption Testing** – i.i.d, collinearity (VIF), linearity, error variance, normality.  
6. **Robustness Checks** – heteroscedasticity-robust standard errors, Cook’s distance.  

---

## 📈 Results
- **Weekend effect:** Articles published on weekends saw a **34–37% increase** in shares.  
- **Significance:** `is_weekend` coefficient was highly significant (p < 0.001).  
- **Model performance:** Adjusted R² ≈ 0.058 (low explanatory power).  
- **Key Insight:** While weekends positively impact shares, many other unobserved factors influence popularity.  

---

## ⚠️ Limitations
- **IID violation:** Possible interdependence between articles (recommendation systems, trending topics).  
- **Omitted variables:** Author, reader demographics, social media trends, timing of publication.  
- **Model assumptions:** Violations in linearity, homoscedasticity, and normality of residuals.  
- **Predictive power:** Low R² suggests results should be interpreted with caution.  

---

## ✅ Conclusion
- Publishing entertainment articles on **weekends** increases shares by **~34%** compared to weekdays.  
- However, due to low model fit, **publication timing alone is not enough** to explain popularity.  
- Future work should include **non-linear models** and additional explanatory variables (e.g., social media signals, author influence, breaking news effects).  

---

## 👥 Team
This project was created by the UC Berkeley MIDS (Master of Information and Data Science) student 
- Agnese, Minazzo
- Etienne, Ndedi
- Tingting, Li