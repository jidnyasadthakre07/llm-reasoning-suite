# 🧠 LLM Reasoning Suite: Chain-of-Thought & Tree-of-Thought Prompt Engineering

> An AI-powered project demonstrating how Large Language Models (LLMs) can perform explainable sentiment analysis and intelligent machine learning model selection using Chain-of-Thought (CoT) and Tree-of-Thought (ToT) reasoning techniques.

---

## 📌 Project Overview

This repository implements two practical applications of Prompt Engineering using modern LLMs:

### Task 1: Sentiment Analysis using Chain-of-Thought (CoT)

A Streamlit application that uses **Google Gemini 2.5 Flash Lite** to analyze customer reviews and predict sentiment while explaining the reasoning behind the prediction.

### Task 2: Hyperparameter Selection using Tree-of-Thought (ToT)

A Streamlit application that uses **Groq Llama 3.3 70B** to analyze machine learning hyperparameter tuning results and recommend the best model configuration through structured multi-branch reasoning.

---

## 🎯 Objectives

### Chain-of-Thought Sentiment Analysis

* Analyze customer reviews
* Detect positive and negative phrases
* Identify mixed sentiments
* Determine overall sentiment
* Generate explainable reasoning

### Tree-of-Thought Hyperparameter Analysis

* Evaluate multiple model configurations
* Compare performance metrics
* Analyze bias-variance tradeoffs
* Assess model stability
* Recommend the best configuration

---

# 🏗️ Project Architecture

```text
Customer Reviews
       │
       ▼
Gemini 2.5 Flash Lite
       │
Chain-of-Thought Prompting
       │
       ▼
Sentiment Classification
       │
       ▼
Explainable Reasoning


AQI Dataset
       │
       ▼
Random Forest Regressor
       │
RandomizedSearchCV
       │
       ▼
AQI_Model_Results.csv
       │
       ▼
Groq Llama 3.3 70B
       │
Tree-of-Thought Prompting
       │
       ▼
Best Hyperparameter Recommendation
```

---

# 📂 Repository Structure

```text
llm-reasoning-suite/
│
├── app_task1.py              # CoT Sentiment Analysis App
├── app_task2.py              # ToT Hyperparameter Analysis App
├── ml.py                     # Random Forest Training Pipeline
├── AQI.csv                   # Air Quality Dataset
├── AQI_Model_Results.csv     # Hyperparameter Tuning Results
├── requirements.txt          # Project Dependencies
├── .env                      # API Keys (not committed)
└── README.md
```

---

# 🚀 Task 1: Sentiment Analysis using Chain-of-Thought

## Problem Statement

Given a customer review, use an LLM to:

* Predict sentiment

  * Positive
  * Neutral
  * Negative
* Explain the decision using step-by-step reasoning.

---

## Technology Stack

| Component | Technology            |
| --------- | --------------------- |
| Frontend  | Streamlit             |
| LLM       | Gemini 2.5 Flash Lite |
| SDK       | google-generativeai   |
| Language  | Python                |

---

## Chain-of-Thought Prompt Design

The model follows a structured reasoning process:

### Step 1

Identify positive sentiment phrases.

Example:

```text
excellent quality
great packaging
fast delivery
```

### Step 2

Identify negative sentiment phrases.

Example:

```text
poor quality
late delivery
damaged product
```

### Step 3

Check for mixed opinions.

Example:

```text
Good quality but delivery was very slow.
```

### Step 4

Analyze emotional tone.

### Step 5

Predict final sentiment.

### Step 6

Generate explanation.

---

## Features

✅ Review Classification

✅ Explainable AI Responses

✅ Adjustable Temperature

✅ Adjustable Token Limit

✅ Interactive Streamlit UI

---

## Run Task 1

```bash
streamlit run app_task1.py
```

---

# 🌳 Task 2: Hyperparameter Selection using Tree-of-Thought

## Problem Statement

Hyperparameter tuning generates multiple candidate configurations.

Selecting the best configuration requires balancing:

* Performance
* Stability
* Generalization
* Training Cost

Tree-of-Thought reasoning allows the LLM to compare multiple candidate branches before selecting the best model.

---

## Machine Learning Pipeline

### Dataset

Air Quality Index (AQI) Dataset

### Target Variable

```text
AQI
```

### Features Used

```text
PM2.5
PM10
NO2
CO
NOx
SO2
City
```

---

## Data Preprocessing

### Numerical Features

Scaled using:

```python
RobustScaler()
```

### Categorical Features

Encoded using:

```python
OrdinalEncoder()
```

### Combined With

```python
ColumnTransformer()
```

---

## Model

```python
RandomForestRegressor
```

---

## Hyperparameter Search Space

```python
n_estimators = [50, 100, 150]

max_depth = [5, 10, 15, None]

min_samples_split = [2, 4, 5]

min_samples_leaf = [1, 2, 4]
```

---

## Hyperparameter Optimization

Method:

```python
RandomizedSearchCV
```

Cross Validation:

```text
5-Fold Cross Validation
```

Metrics Collected:

* Mean Test Score
* Standard Deviation
* Rank Test Score
* Test R² Score
* Training Time

---

## Tree-of-Thought Prompt Design

The LLM evaluates multiple candidate branches.

### Branch Evaluation Criteria

#### Performance

```text
mean_test_score
```

#### Stability

```text
std_test_score
```

#### Generalization

```text
test_r2
```

#### Efficiency

```text
training_time
```

#### Ranking

```text
rank_test_score
```

---

## Output

The LLM provides:

* Best Hyperparameter Configuration
* Top Candidate Analysis
* Rejected Alternatives
* Final Recommendation

---

## Run ML Pipeline

```bash
python ml.py
```

Output:

```text
AQI_Model_Results.csv
```

---

## Run Task 2

```bash
streamlit run app_task2.py
```

Upload:

```text
AQI_Model_Results.csv
```

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/llm-reasoning-suite.git

cd llm-reasoning-suite
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / Mac

```bash
python -m venv venv

source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Environment Variables

Create a `.env` file:

```env
GEMINI_API_KEY=YOUR_GEMINI_API_KEY

GROQ_API_KEY=YOUR_GROQ_API_KEY
```

---

# 📊 Workflow

## Task 1

```text
Customer Review
      ↓
Gemini LLM
      ↓
Chain-of-Thought Reasoning
      ↓
Sentiment Prediction
      ↓
Explanation
```

## Task 2

```text
AQI Dataset
      ↓
Random Forest Training
      ↓
RandomizedSearchCV
      ↓
Results CSV
      ↓
Groq Llama 3.3
      ↓
Tree-of-Thought Analysis
      ↓
Best Configuration
```

---

# 🛠 Technologies Used

* Python
* Streamlit
* Scikit-Learn
* Pandas
* NumPy
* Google Gemini
* Groq
* Llama 3.3 70B
* Random Forest
* RandomizedSearchCV
* Prompt Engineering

---

# 📈 Future Improvements

* Automated Review Scraping
* Few-Shot CoT Examples
* XGBoost Support
* LightGBM Integration
* SHAP Explainability
* Multi-Model Comparison
* FastAPI Deployment
* Docker Containerization
* Cloud Deployment

---

# 🎓 Key Learning Outcomes

This project demonstrates:

* Chain-of-Thought Prompting
* Tree-of-Thought Prompting
* Explainable AI
* LLM Reasoning
* Sentiment Analysis
* Hyperparameter Optimization
* Machine Learning Evaluation
* Streamlit Development
* Gemini API Integration
* Groq API Integration

---

# 🏆 Conclusion

This project showcases how Large Language Models can be used as reasoning engines rather than simple text generators. By combining Prompt Engineering, Machine Learning, and Explainable AI techniques, the system provides transparent sentiment analysis and intelligent model-selection recommendations through structured reasoning workflows.

---

## Author

**Jidnyasa Thakre**

GitHub: https://github.com/jidnyasadthakre07

LinkedIn: https://www.linkedin.com/in/jidnyasathakre/
