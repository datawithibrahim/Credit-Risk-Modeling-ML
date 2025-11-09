#  Credit Risk Prediction Using Machine Learning

###  Project Overview & Business Context

Credit risk assessment is a cornerstone of every financial institution. Lenders face major financial losses when loans are given to applicants who default. Traditionally, credit analysts rely on manual reviews of applications  a process that’s time-consuming, subjective, and prone to inconsistency.

This project aimed to **automate and modernize** credit risk evaluation using **machine learning**.  
The goal was to predict whether a loan applicant is likely to be a **Good Credit (low risk)** or **Bad Credit (high risk)** borrower, enabling institutions to make **faster, fairer, and data-driven decisions**.

> This project combines financial reasoning with data science blending model interpretability, business logic, and responsible automation.



## Problem Statement

Can a machine learning model classify an applicant’s credit risk level (good/bad) **as reliably or better** than traditional manual methods?

**Key Goals:**
- ⏱️ Reduce loan application processing time  
- 🧩 Minimize human bias and subjectivity  
- ⚖️ Ensure fairness and consistency in decisions  
- 💡 Lower default rates through smarter, data-backed predictions  



##  Dataset Description & Features

The dataset used is the **German Credit Risk Dataset**, a benchmark dataset widely applied in financial ML research.  
Each record represents a loan applicant with multiple attributes such as age, job, savings, housing, and loan amount.

| Feature | Description |
|----------|--------------|
| **Age** | Applicant’s age (proxy for earning stability and maturity) |
| **Sex** | Gender as recorded in the application |
| **Job** | Occupation skill level (0–3, higher = lower risk) |
| **Housing** | Living situation (own, rent, free) |
| **Saving Accounts** | Categories indicating liquidity (“little”, “moderate”, “rich”) |
| **Checking Account** | Active account status with balance range |
| **Credit Amount** | Loan amount requested |
| **Duration** | Loan term in months |
| **Purpose** | Reason for loan (e.g., car, education, furniture) |

**Target Variable:**
- `1` → Good Credit (Low Risk)  
- `0` → Bad Credit (High Risk)



##  Tools, Technologies & Environment

| Category | Tools/Frameworks |
|-----------|------------------|
| **Language** | Python |
| **Libraries** | Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn |
| **Modeling** | Decision Tree, Random Forest, Extra Trees |
| **Preprocessing** | LabelEncoder, Joblib |
| **Visualization** | Seaborn, Matplotlib |
| **Deployment** | Streamlit + Ngrok |
| **Environment** | Google Colab |



## Data Preprocessing & Feature Engineering

**Handling Missing Values:**  
- Missing entries (e.g., savings/checking accounts) were filled using **mode imputation** to retain data integrity.  

**Encoding Categorical Data:**  
- Used **LabelEncoder** for categorical columns.  
- Created and saved **individual encoders** for consistent category mapping between training and deployment stages.  

**Scaling & Transformation:**  
- Skipped scaling to maintain interpretability and to leverage ExtraTreesClassifier’s scale-invariance.  



##  Model Building & Selection

Initial exploration included Decision Tree and Random Forest models.  
The final choice was **ExtraTreesClassifier** due to its superior accuracy and interpretability.

**Why ExtraTrees?**
- Reduces overfitting via decorrelated tree ensembles  
- Handles mixed feature types naturally  
- Provides **feature importance ranking**  vital for explainability in banking  

**Hyperparameter Tuning:**  
- Used `GridSearchCV` with **5-fold cross-validation**  
- Tuned parameters like `n_estimators`, `max_depth`, and `min_samples_split`


##  Model Evaluation & Metrics

| Metric | Value | Interpretation |
|--------|--------|----------------|
| **Accuracy** | ~83% | Majority of predictions correct |
| **Precision** | 0.85 | Most “good” predictions are actually good |
| **Recall** | 0.81 | Most “good” customers correctly identified |
| **F1-Score** | 0.83 | Balanced performance |
| **Confusion Matrix** | Balanced | No bias toward any class |

**Business Outcome:**  
The model effectively minimized both **false approvals (bad loans)** and **false rejections (good applicants)**, ensuring fair and practical real-world performance.


##  Model Saving, Pipeline, and Consistency

- Both the trained model and label encoders were **serialized using Joblib**  
- Maintained a **consistent pipeline** from training to prediction  
- Prevented **data transformation drift** between environments  
- Ensured future integration as a microservice or API is seamless  



##  Streamlit Application & Deployment

A **Streamlit app** was developed to simulate real-world banking use.

**App Features:**
- Clean and interactive interface  
- Input fields mirroring actual loan applications  
- Instant prediction output: “Good Credit” or “Bad Credit”  
- Reuse of trained encoders for consistent transformation  

**Deployment:**  
- Hosted via **Google Colab + Ngrok** for live public demo access  
- Enabled zero-infrastructure, cloud-based testing  



##  Real-World Impact

| Area | Impact |
|------|---------|
| **Speed** | Reduced decision time from days → seconds |
| **Fairness** | Eliminated subjective bias |
| **Compliance** | Provided transparent, explainable outputs |
| **Scalability** | Can process 1,000+ applications/minute |
| **Profitability** | Lowered default rates and boosted lending efficiency |

Studies show ML adoption in lending can reduce default rates by up to **40%** and cut onboarding time by **50%**.


##  Challenges Faced & Solutions

| Challenge | Solution |
|------------|-----------|
| Encoder mismatch between train/test | Saved unique encoders per feature using Joblib |
| Hyperparameter tuning errors | Debugged GridSearchCV logs carefully |
| Ngrok authentication issues | Resolved with proper token setup and validation |
| Data type inconsistencies | Implemented schema validation and clean encoding |

##  Learning Outcomes & Insights

| Area | Key Takeaway |
|-------|---------------|
| **Data Quality** | Even minor formatting errors can break entire pipelines |
| **Feature Engineering** | Consistency in encoding ensures production reliability |
| **Model Selection** | Ensemble models outperform individual learners |
| **Usability** | Streamlit simplifies ML adoption for non-technical users |
| **Deployment** | Saving full pipelines is critical for live stability |


##  Conclusion & Future Scope

This project demonstrates an **end-to-end ML workflow** — from data exploration to deployment.  
It reflects how **AI-driven credit scoring** can reshape financial decision-making by making it faster, unbiased, and explainable.

**Future Enhancements:**
- Integrate **Explainable AI (XAI)** for transparency  
- Deploy on **AWS / Heroku** for permanent hosting  
- Add **real-time dashboard** for loan portfolio monitoring  

> A complete production-ready showcase of Data Science applied to FinTech — balancing business sense, model integrity, and practical usability.

---


**Ibrahim Shaikh**  
📍 Data Science & Analyst   
📧 ibrahimsh1910@gmail.com  
💼 [LinkedIn Profile](https://www.linkedin.com/in/your-profile)  

---



