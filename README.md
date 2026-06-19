# ⚡ EV Charging Station DES Cost-Profit Optimization

## 📌 Project Overview
This project focuses on optimizing the operations of an Electric Vehicle (EV) charging station at a highway rest area using **Discrete Event Simulation (DES)** in Python. 
By simulating various scenarios, this study evaluates both **operational efficiency** (waiting times, customer loss rate) and **economic viability** (cost-profit optimization) to determine the best infrastructure expansion strategy.

## 🧑‍💻 Author
* **Hwisu Kim** (Industrial and Data Engineering)
* Contact: [Your Email Address]

## 🎯 Key Features & Assumptions
* **Behavior-Based Routing:** Customers choose chargers based on real-time queue lengths or pre-assigned priority.
* **Priority Queue System:** Implementation of premium priority access, analyzing its impact on customer retention and snack purchase probability based on waiting times.
* **Cost-Profit Optimization:** Balancing infrastructure expansion costs (Ultra-fast/Fast chargers depreciation and maintenance) against expected revenue from charging fees and retail sales.

## 📊 Key Findings
1. **Operational Efficiency:** Scenario 2 (Adding 1 more Ultra-fast charger) drastically reduced the average waiting time by **73%** (from 0.92 min to 0.25 min) and the customer loss rate by **97.1%**.
2. **Economic Viability:** Despite the operational benefits of Scenario 2, **Scenario 1 (Baseline: 4 Ultra-fast, 4 Fast chargers)** was proven to be the most economically optimal choice. The high initial installation and maintenance costs of new chargers outweighed the marginal increase in revenue from additional customers.

## 📂 Repository Structure
* `docs/`: Contains the final project report and presentation slides (PDF).
* `src/`: Contains the Python simulation source code (`.ipynb`).
