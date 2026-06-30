<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=30,31,32&height=180&section=header&text=Spread%20Locator&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Statistical%20Distribution%20Analysis%20Model&descAlignY=55&descSize=18" />
</div>

A complete **Theory + Practical Statistics Project** that applies **Probability Distributions** to a real-world financial transaction dataset containing customer transaction records.

The project explores important statistical distributions including **Bernoulli, Binomial, Geometric, Poisson, Uniform, Normal, Exponential, Gamma, Beta, Log-Normal, and Power Law distributions** to analyze transaction behavior and derive meaningful business insights.

The complete analysis is implemented using **Python (Jupyter Notebook)** with detailed explanations, mathematical formulas, visualizations, statistical interpretations, and business-oriented conclusions.

---

# 🎯 Objective

To understand customer transaction behavior by applying probability distributions and statistical techniques on financial transaction data. The project demonstrates how different probability models can represent real-world business scenarios and support data-driven decision making.

---

# 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 spread_locator.ipynb | Complete Probability Distribution Analysis |
| 📊 spread_locator_dataset.xlsx | Financial transaction dataset |
| 📄 Probability_Distributions_Theory.pdf | Theory, formulas, and explanations |
| 🖼️ Diagrams | Theory diagrams and illustrations |
| 📘 README.md | Project documentation |

---

# 🛠️ Tools Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- OpenPyXL

---

# 🎬 Project Demo

📹 Complete walkthrough of the project demonstrating every probability distribution and interpretation.

---

# 🖼️ Theory Topics Covered

### Q1. What is Probability?

### Q2. Random Variable

### Q3. Bernoulli Distribution

### Q4. Binomial Distribution

### Q5. Geometric Distribution

### Q6. Poisson Distribution

### Q7. Uniform Distribution

### Q8. Normal Distribution

### Q9. Exponential Distribution

### Q10. Gamma Distribution

### Q11. Beta Distribution

### Q12. Log-Normal Distribution

### Q13. Power Law Distribution

---

# 📗 Statistical Topics Covered

---

# 🔬 Q1 — Bernoulli Distribution

## Objective

Model whether a transaction was **Successful (1)** or **Failed (0)**.

### Python Code

```python
df["transaction_occurrence"] = df["transaction_status"].map({
    "Success":1,
    "Fail":0
})

success_probability = df["transaction_occurrence"].mean()
```

### Interpretation

Each transaction has only two possible outcomes:

- Success
- Failure

Bernoulli Distribution models this binary event.

### Conclusion

The Bernoulli model estimates the probability of a successful transaction.

---

# 📊 Q2 — Binomial Distribution

## Objective

Model the number of successful transactions within multiple transaction attempts.

### Python Code

```python
from scipy.stats import binom

n = 10
p = success_probability

x = np.arange(0,n+1)

binomial = binom.pmf(x,n,p)
```

### Interpretation

The Binomial Distribution calculates the probability of obtaining different numbers of successful transactions over multiple attempts.

### Conclusion

Useful for predicting customer success rates over repeated transactions.

---

# 📈 Q3 — Geometric Distribution

## Objective

Estimate the probability of obtaining the first successful transaction.

### Python Code

```python
from scipy.stats import geom

x = np.arange(1,11)

geom_prob = geom.pmf(x,p)
```

### Interpretation

The Geometric Distribution models how many attempts are required before the first successful transaction occurs.

### Conclusion

Useful for studying customer conversion behavior.

---

# 📊 Q4 — Poisson Distribution

## Objective

Model the number of transactions occurring during a fixed period.

### Python Code

```python
from scipy.stats import poisson

lam = df["transaction_count"].mean()

poisson_prob = poisson.pmf(x,lam)
```

### Interpretation

Poisson Distribution models rare events occurring within fixed intervals.

### Conclusion

Suitable for analyzing transaction frequency.

---

# 📈 Q5 — Uniform Distribution

## Objective

Model evenly distributed transaction amounts.

### Python Code

```python
from scipy.stats import uniform
```

### Interpretation

Every value inside the specified range has an equal probability of occurring.

### Conclusion

Provides a baseline probability model for equally likely values.

---

# 📊 Q6 — Normal Distribution

## Objective

Determine whether transaction amounts follow a bell-shaped distribution.

### Python Code

```python
from scipy.stats import norm

mu = df["transaction_amount"].mean()
sigma = df["transaction_amount"].std()
```

### Interpretation

The Normal Distribution evaluates whether transaction amounts are centered around the average.

### Conclusion

Useful for identifying typical customer spending behavior.

---

# 📈 Q7 — Exponential Distribution

## Objective

Analyze waiting time between customer transactions.

### Python Code

```python
from scipy.stats import expon
```

### Interpretation

Models the time interval between independent transaction events.

### Conclusion

Useful for transaction arrival analysis.

---

# 📊 Q8 — Gamma Distribution

## Objective

Model positively skewed transaction amounts.

### Python Code

```python
from scipy.stats import gamma
```

### Interpretation

Gamma Distribution effectively models continuous positive financial values.

### Conclusion

Suitable for transaction amount analysis.

---

# 📈 Q9 — Beta Distribution

## Objective

Analyze transaction success probabilities.

### Python Code

```python
from scipy.stats import beta
```

### Interpretation

Beta Distribution models probabilities between 0 and 1.

### Conclusion

Useful for probability estimation and Bayesian analysis.

---

# 📊 Q10 — Log-Normal Distribution

## Objective

Determine whether transaction amounts follow a Log-Normal Distribution.

### Python Code

```python
from scipy.stats import lognorm
```

### Interpretation

Financial transaction values often follow a Log-Normal Distribution because values are always positive and right-skewed.

### Conclusion

Provides a realistic model for transaction amount distributions.

---

# 📈 Q11 — Power Law Distribution

## Objective

Study heavy-tailed transaction behavior.

### Python Code

```python
from scipy.stats import powerlaw
```

### Interpretation

A small number of customers contribute very large transaction amounts, while most contribute relatively small amounts.

### Conclusion

Useful for identifying high-value customers and spending patterns.

---

# 📊 Additional Statistical Analysis

✔️ Q-Q Plot for Normality Testing

✔️ Box-Cox Transformation

✔️ Z-Score Analysis

✔️ Probability of Transactions Exceeding Threshold

✔️ Probability Density Function (PDF)

✔️ Cumulative Distribution Function (CDF)

✔️ Distribution Comparison

✔️ Best Fit Distribution Analysis

---

# 📊 Key Findings

✔️ Transaction success and failure were effectively modeled using the Bernoulli Distribution.

✔️ Customer transaction frequencies followed the Binomial and Poisson distributions.

✔️ Waiting time between transactions was analyzed using the Exponential Distribution.

✔️ Transaction amounts were compared across Normal, Gamma, Log-Normal, and Power Law distributions.

✔️ Q-Q Plot and Box-Cox Transformation were used to evaluate normality.

✔️ Z-Score analysis identified unusually high transaction values.

✔️ PDF and CDF visualizations helped understand probability behavior.

✔️ The best-fitting probability distribution was identified based on statistical analysis.

✔️ Probability distributions transformed raw transaction data into meaningful business insights.

---

# 🎯 Final Conclusion

**Spread Locator** successfully demonstrates the application of probability distributions to real-world financial transaction data. The project explores discrete and continuous probability models including Bernoulli, Binomial, Geometric, Poisson, Uniform, Normal, Exponential, Gamma, Beta, Log-Normal, and Power Law distributions.

Using Python, statistical visualization, and distribution fitting techniques, the project provides a comprehensive understanding of transaction behavior, customer activity, and probability modeling. The analysis highlights how statistical methods can support evidence-based business decisions and improve financial data analysis.

---

# 🚀 How to Run

Install the required libraries:

```bash
pip install pandas numpy scipy matplotlib seaborn openpyxl
```

Open Jupyter Notebook:

```bash
jupyter notebook
```

Run:

```text
spread_locator.ipynb
```

---

# ✅ Submission Checklist

- Probability Theory
- Random Variables
- Bernoulli Distribution
- Binomial Distribution
- Geometric Distribution
- Poisson Distribution
- Uniform Distribution
- Normal Distribution
- Exponential Distribution
- Gamma Distribution
- Beta Distribution
- Log-Normal Distribution
- Power Law Distribution
- Q-Q Plot Analysis
- Box-Cox Transformation
- Z-Score Analysis
- PDF & CDF Visualization
- Best Distribution Identification
- Statistical Interpretations
- Dataset Included
- Jupyter Notebook Included
- Theory Report Included
- README Documentation Included

---

# 👩‍💻 Shruti Bhawsar

📍 Ahmedabad, Gujarat, India

⭐ If you found this project helpful, consider giving it a **Star ⭐** and feel free to **Fork 🍴** the repository.

### 📊 Probability Distributions • Statistical Modeling • Financial Data Analysis • Data-Driven Decisions
