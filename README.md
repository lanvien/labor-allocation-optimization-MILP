# 🏗️ Labor Allocation Optimization: The Aunt vs. The Algorithm

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/lanvien/labor-allocation-optimization-MILP/blob/main/optimization_research.ipynb)

### 💡 The Story
During the construction of a cable car system, I observed **300+ workers** allocated purely through human intuition - a seasoned site manager (**“the Aunt”**) making reassignment decisions based on experience.

**This project formalizes a central question:**
> *Can mathematical optimization outperform instinct - and under what constraints does instinct win?*

To answer this, I introduce the **Switching Cost ($\beta$)** — a quantifiable friction term capturing the organizational cost of worker reassignment.

---

### 🎯 Research Objective
This study compares two distinct approaches to labor logistics:
* **Mixed-Integer Linear Programming (MILP):** A rigorous mathematical approach to find the global minimum.
* **Greedy Human Heuristic:** A simulation of intuitive, experience-based allocation.

The goal is **not to eliminate intuition**, but to model when *human stability* becomes mathematically optimal.

---

### 🛠️ Methodology

#### 1️⃣ Optimization Model (MILP)
Using the `PuLP` library, I formulated a multi-objective MILP:

$$Z = \sum \text{Travel Costs} + \alpha \cdot \sum \text{Skill Gaps} + \beta \cdot \sum \text{Reassignments}$$

**Where:**
* **Travel Costs:** Distance and time inefficiencies.
* **Skill Gaps ($\alpha$):** Mismatch penalties between worker ability and task requirements.
* **Reassignments ($\beta$):** The "Switching Friction" representing organizational entropy.

#### 2️⃣ Stochastic Simulation
To reflect real-world construction uncertainty, I implemented:
* **1,000 Monte Carlo simulations** to test model robustness.
* **Gaussian noise** injection into worker skill matrices (simulating fatigue/weather).
* **Comparative analysis** of cost distributions across various $\beta$ scenarios.

---

### 📊 Key Findings

* **Efficiency in Stable Environments:** MILP reduced total operational costs by **10–15%** on average when the Switching Cost ($\beta$) was low.
* **Resilience Under High Switching Cost:** As $\beta$ increases, frequent reassignment becomes destabilizing. The **Greedy Heuristic** showed lower variance, proving that **stability acts as a hidden optimization constraint.**

> **Insight:** Optimization is not purely mathematical — it is *socio-technical*.

---

### 🧠 Conceptual Contribution
This project reframes labor allocation as a trade-off between **Mathematical Efficiency** and **Organizational Entropy**. It bridges:
* **Operations Research:** Quantitative decision-making.
* **Infrastructure Systems:** Real-world logistics constraints.
* **Behavioral Modeling:** Quantifying the "human factor" in engineering.

---

### 🧰 Tech Stack
* **Language:** `Python 3.x`
* **Optimization:** `PuLP` (MILP Solver)
* **Data & Simulation:** `NumPy`, `Random` (Monte Carlo)
* **Visualization:** `Matplotlib`
