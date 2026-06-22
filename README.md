# ⚡ EV Charging Station DES Cost-Profit Optimization

## 📌 Project Overview
This project focuses on optimizing the operations of an Electric Vehicle (EV) charging station at a highway rest area using **Discrete Event Simulation (DES)**. 
By simulating various scenarios, this study evaluates both **operational efficiency** (waiting times, customer loss rate) and **economic viability** (cost-profit optimization) to determine the optimal infrastructure expansion strategy.

## 🧑‍💻 Author
* **Hwisu Kim** (Industrial and Data Engineering)
* Contact: hwisu03@gmail.com

## 🛠 Tech Stack & Methodologies
* **Language:** Python
* **Methodologies:** Discrete Event Simulation (DES), Queueing Theory (Priority Queues, Balking/Blocking)

## 🎯 Key Features & Assumptions
* **State-Dependent Behavior:** Customers evaluate the Estimated Waiting Time (EWI) upon arrival to make decisions on balking or purchasing premium priority tickets, modeled via a **Step Function**.
* **Priority Queue System:** Implemented a non-preemptive priority discipline for ticket holders, analyzing its impact on customer retention and secondary revenue (e.g., rest area snack purchases proportional to sojourn time).
* **Dynamic Charging Times:** Calculated realistic service rates ($\mu$) using battery capacities, initial state-of-charge distributions ($Beta(2, 5)$), and charger efficiencies.
* **Cost-Profit Optimization:** Balanced infrastructure expansion costs (depreciation and maintenance for Ultra-fast/Fast chargers) against expected revenue from charging fees and retail sales.

## 📊 Key Findings
1. **Operational Efficiency:** Scenario 2 (Adding 1 Ultra-fast charger) drastically reduced the average waiting time by **73%** (from 0.92 min to 0.25 min) and the customer loss rate by **97.1%**.
2. **Economic Viability:** Despite the operational benefits of Scenario 2, **Scenario 1 (Baseline: 4 Ultra-fast, 4 Fast chargers)** proved to be the most economically optimal choice. The high initial installation and maintenance costs of new chargers outweighed the marginal increase in revenue from additional customers.

## 📂 Repository Structure
* `docs/Simulation_Proposal.pdf`: Initial DES mathematical modeling and proposal.
* `docs/Simulation_Project.pdf`: Final project report.
* `src/`: Contains the Python simulation source code (`.ipynb`).

## 📝 Retrospective: Errata in Initial Proposal
In the initial proposal (`docs/Simulation_Proposal.pdf`), the System State for the $M(t)/G/2/K$ queue was defined as $SS = (n, i_1, i_2)$, calling the next queued vehicle using the formula $m = \max(i_1, i_2) + 1$. 
While this mathematical logic is perfectly valid for an infinite capacity system where IDs are sequential, it contains a logical flaw in a space-constrained system ($K$). When a vehicle is lost due to capacity overflow (Balking), the ID sequence breaks, causing the $m+1$ logic to call a "ghost vehicle" that has already left the system. This insight highlights the necessity of using explicit Queue data structures rather than purely arithmetic ID calculations, a flaw that was successfully debugged and implemented in the final Python model.

## 🚧 Limitations and Future Work
* **Assumption of Homogeneous Traffic:** The current discrete-event simulation model assumes a Homogeneous Poisson Process for vehicle arrivals, utilizing a fixed arrival rate ($\lambda$). As a result, the incoming traffic was evenly distributed across the total simulation timeframe ($N=5,000$), preventing severe bottleneck phenomena.

* **Future Implementation of NHPP:** In reality, highway charging stations experience extreme traffic surges during specific periods (e.g., peak commuting hours, national holidays). For future iterations, the model will be advanced by applying a **Non-homogeneous Poisson Process (NHPP)** with a time-varying arrival rate ($\lambda(t)$) to better capture and optimize realistic bottleneck scenarios.
