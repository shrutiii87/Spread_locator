
<div align="center">

  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=30,31,32&height=180&section=header&text=Spread%20Locator&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Statistical%20Distribution%20Analysis%20Model&descAlignY=55&descSize=18" />

</div>

A complete Theory + Practical Statistics Project that applies Probability Distributions to a real-world financial transaction dataset containing customer transaction records.

to understand and apply the concepts of probability distributions and spread analysis on a given dataset. This will test theoretical understanding and practical application of distribution types, Q-Q plots, statistical transformations, and probability functions.

The complete analysis is implemented using Python (Jupyter Notebook) with detailed explanations, mathematical formulas, visualizations, statistical interpretations, and business-oriented conclusions.

---

🎯 Objective

an e-commerce platform that wants to understand customer purchase behaviors by analyzing daily transaction amounts of customers. Management is particularly interested in knowing whether the transactions follow certain statistical distributions, how to handle skewed data, and what probability insights can be derived.

Your task is to apply statistical distribution concepts and transformations to derive insights on transaction behaviors.

---

<img width="960" height="540" alt="Screenshot 2026-07-01 122834" src="https://github.com/user-attachments/assets/087df644-5361-43d9-82e6-705ae2c2ec84" />

---

🗂️ Project Files

| File | Description |

|------|-------------|

| 📓 spread_locator.ipynb | Complete Probability Distribution Analysis |

| 📊 spread_locator_dataset.xlsx | Financial transaction dataset |

| 📄 Probability_Distributions_Theory.pdf | Theory, formulas, and explanations |

| 🖼️ Diagrams | Theory diagrams and illustrations |

| 📘 README.md | Project documentation |

---

🛠️ Tools Used

<p align="center">

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>

<img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>

<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>

<img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>

<img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white"/>

<img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white"/>

<img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white"/>

</p>

---

🎬 Project Demo

📹 Complete walkthrough of the project demonstrating every probability distribution and interpretation.

---

🖼️ Theory Topics Covered

Q2. What is a Q-Q Plot and Why Is It Used?

<p align="center">

  <img src="https://github.com/user-attachments/assets/69628f94-0223-4c10-a291-89913f3fb735" width="700">

</p>

Q3. Difference Between Discrete and Continuous Distributions

<p align="center">

  <img src="https://github.com/user-attachments/assets/1b14a015-13f6-4fe9-a63d-edaf3fcf4c77" width="700">

</p>

Q4. What Is Bernoulli Distribution?

<p align="center">

  <img src="https://github.com/user-attachments/assets/78d1af7d-a98d-4aca-b472-75ca132e51bd" width="700">

</p>

Q5. What Is Binomial Distribution?

<p align="center">

  <img src="https://github.com/user-attachments/assets/8679aa2f-6a8a-4e83-aea6-f21a0394f506" width="700">

</p>

Q6. Explain Log-Normal Distribution

<p align="center">

  <img src="https://github.com/user-attachments/assets/324c95a8-9528-44da-a4a0-1f48deb92d76" width="700">

</p>

Q7. Explain Power Law Distribution

<p align="center">

  <img src="https://github.com/user-attachments/assets/f3e26dd6-0cdf-4683-b7d9-185b564a39fb" width="700">

</p>

Q8. What Is Box-Cox Transform?

<p align="center">

  <img src="https://github.com/user-attachments/assets/ea307d23-558f-496f-9dc2-b713d2439b64" width="700">

</p>

Q9. Explain Poisson Distribution with an Example

<p align="center">

  <img src="https://github.com/user-attachments/assets/8c0e4030-14cd-4140-a408-e49dad9f00a5" width="700">

</p>

Q10. What Is Z-Score Probability?

<p align="center">

  <img src="https://github.com/user-attachments/assets/897599da-39c3-454c-92cb-608568553df8" width="700">

</p>

Q11. Difference Between Probability Density Function (PDF) and Cumulative Distribution Function (CDF)

<p align="center">

  <img src="https://github.com/user-attachments/assets/910e8361-44db-49c8-8c6a-b39cb1f70268" width="700">

</p>

---

📗 Statistical Topics Covered

---

imported libraries

```python

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

import pandas as pd

from scipy.stats import poisson,lognorm, powerlaw, boxcox , zscore, norm

import statsmodels.api as sm

```

---

🔬 Q1 — Bernoulli Distribution

Objective

Model whether a transaction was Successful (1) or Failed (0).

Python Code

```python

df["transaction_occurrence"] = df["transaction_status"].map({

    "Success":1,

    "Fail":0

})

success_probability = df["transaction_occurrence"].mean()

```

Interpretation

Each transaction has only two possible outcomes:

- Success

- Failure

Bernoulli Distribution models this binary event.

Conclusion

The Bernoulli model estimates the probability of a successful transaction.

---

📊 Q2 — Binomial Distribution

Objective

Model the number of successful transactions within multiple transaction attempts.

Python Code

```python

from scipy.stats import binom

n = 10

p = success_probability

x = np.arange(0,n+1)

binomial = binom.pmf(x,n,p)

```

Interpretation

The Binomial Distribution calculates the probability of obtaining different numbers of successful transactions over multiple attempts.

Conclusion

Useful for predicting customer success rates over repeated transactions.

---

📈 Q3 — Geometric Distribution

Objective

Estimate the probability of obtaining the first successful transaction.

Python Code

```python

from scipy.stats import geom

x = np.arange(1,11)

geom_prob = geom.pmf(x,p)

```

Interpretation

The Geometric Distribution models how many attempts are required before the first successful transaction occurs.

Conclusion

Useful for studying customer conversion behavior.

---

📊 Q4 — Poisson Distribution

Objective

Model the number of transactions occurring during a fixed period.

Python Code

```python

from scipy.stats import poisson

lam = df["transaction_count"].mean()

poisson_prob = poisson.pmf(x,lam)

```

Interpretation

Poisson Distribution models rare events occurring within fixed intervals.

Conclusion

Suitable for analyzing transaction frequency.

---

📈 Q5 — Uniform Distribution

Objective

Model evenly distributed transaction amounts.

Python Code

```python

from scipy.stats import uniform

```

Interpretation

Every value inside the specified range has an equal probability of occurring.

Conclusion

Provides a baseline probability model for equally likely values.

---

📊 Q6 — Normal Distribution

Objective

Determine whether transaction amounts follow a bell-shaped distribution.

Python Code

```python

from scipy.stats import norm

mu = df["transaction_amount"].mean()

sigma = df["transaction_amount"].std()

```

Interpretation

The Normal Distribution evaluates whether transaction amounts are centered around the average.

Conclusion

Useful for identifying typical customer spending behavior.

---

📈 Q7 — Exponential Distribution

Objective

Analyze waiting time between customer transactions.

Python Code

```python

from scipy.stats import expon

```

Interpretation

Models the time interval between independent transaction events.

Conclusion

Useful for transaction arrival analysis.

---

📊 Q8 — Gamma Distribution

Objective

Model positively skewed transaction amounts.

Python Code

```python

from scipy.stats import gamma

```

Interpretation

Gamma Distribution effectively models continuous positive financial values.

Conclusion

Suitable for transaction amount analysis.

---

📈 Q9 — Beta Distribution

Objective

Analyze transaction success probabilities.

Python Code

```python

from scipy.stats import beta

```

Interpretation

Beta Distribution models probabilities between 0 and 1.

Conclusion

Useful for probability estimation and Bayesian analysis.

---

📊 Q10 — Log-Normal Distribution

Objective

Determine whether transaction amounts follow a Log-Normal Distribution.

Python Code

```python

from scipy.stats import lognorm

```

Interpretation

Financial transaction values often follow a Log-Normal Distribution because values are always positive and right-skewed.

Conclusion

Provides a realistic model for transaction amount distributions.

---

📈 Q11 — Power Law Distribution

Objective

Study heavy-tailed transaction behavior.

Python Code

```python

from scipy.stats import powerlaw

```

Interpretation

A small number of customers contribute very large transaction amounts, while most contribute relatively small amounts.

Conclusion

Useful for identifying high-value customers and spending patterns.

---

📊 Additional Statistical Analysis

✔️ Q-Q Plot for Normality Testing

✔️ Box-Cox Transformation

✔️ Z-Score Analysis

✔️ Probability of Transactions Exceeding Threshold

✔️ Probability Density Function (PDF)

✔️ Cumulative Distribution Function (CDF)

✔️ Distribution Comparison

✔️ Best Fit Distribution Analysis

---

📊 Key Findings

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

🎯 Final Conclusion

Spread Locator successfully demonstrates the application of probability distributions to real-world financial transaction data. The project explores discrete and continuous probability models including Bernoulli, Binomial, Geometric, Poisson, Uniform, Normal, Exponential, Gamma, Beta, Log-Normal, and Power Law distributions.

Using Python, statistical visualization, and distribution fitting techniques, the project provides a comprehensive understanding of transaction behavior, customer activity, and probability modeling. The analysis highlights how statistical methods can support evidence-based business decisions and improve financial data analysis.

---

🚀 How to Run

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

👩‍💻 Shruti Bhawsar

📍 Ahmedabad, Gujarat, India

⭐ If you found this project helpful, consider giving it a Star ⭐ and feel free to Fork 🍴 the repository.

📊 Probability Distributions • Statistical Modeling • Financial Data Analysis • Data-Driven Decisions
