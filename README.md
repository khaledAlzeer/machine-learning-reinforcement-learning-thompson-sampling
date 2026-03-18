# Reinforcement Learning — Thompson Sampling

---

## Overview

Reinforcement Learning is a powerful branch of Machine Learning used to solve interacting problems where the data observed up to time **t** is considered to decide which action to take at time **t + 1**.

It is also used for Artificial Intelligence when training machines to perform tasks such as walking. Desired outcomes provide the AI with reward, undesired with punishment. Machines learn through trial and error.

In this repository, the following Reinforcement Learning model is implemented:

- **Thompson Sampling**

---

## Problem Description

A business wants to know which of **10 different ads** generates the most clicks from users. Instead of testing all ads equally (which wastes budget), Thompson Sampling uses Bayesian inference — maintaining a probability distribution for each ad and sampling from it to balance exploration and exploitation.

---

## Dataset

| Property    | Details                               |
|-------------|---------------------------------------|
| **File**    | `Ads_CTR_Optimisation.csv`            |
| **Rows**    | 10,000 users (rounds)                 |
| **Columns** | 10 ads                                |
| **Values**  | Binary (1 = clicked, 0 = not clicked) |

Each row represents a user. Each column represents whether that user would have clicked a specific ad. Thompson Sampling selects one ad per round without seeing the full row — simulating a real-world online decision.

---

## Notebook Structure
```
Table of Contents
│
├── 1. Importing the libraries
├── 2. Importing the dataset
├── 3. Implementing Thompson Sampling
└── 4. Visualising the results
    ├── 4a. Histogram
    └── 4b. Cumulative Line Plot
```

---

## Visualisations

- **Histogram** — shows how many times each ad was selected across all 10,000 rounds
- **Cumulative Line Plot** — shows how Thompson Sampling rapidly converges toward the best ad over time

---

## Requirements
```bash
pip install numpy pandas matplotlib
```

---

## How to Run

1. Clone the repository
2. Upload `Ads_CTR_Optimisation.csv` to your Colab environment
3. Open the notebook and run all cells top to bottom

---

## Results

Thompson Sampling successfully identifies the best-performing ad within the first ~500 rounds and continues to exploit it for the remaining 9,500 rounds — converging faster than UCB due to its Bayesian exploration strategy.
