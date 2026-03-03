# Labor Allocation Optimization: The Aunt vs. The Algorithm

This research investigates the tension between mathematical optimization (**MILP**) and human heuristic intuition in large-scale infrastructure projects (specifically cable car construction).

### 🚀 Check out the interactive research here:
[Open in Colab](https://colab.research.google.com/github/lanvien/labor-allocation-optimization-MILP/blob/main/optimization_research.ipynb)

### 📊 Methodology & Key Findings
- **The Problem:** 300+ workers managed by "instinctive" decisions often lead to sub-optimal allocation.
- **The Model:** Formulated a Mixed-Integer Linear Programming (MILP) objective to minimize travel costs while maintaining system robustness.
- **The Stress Test:** Conducted **1,000 Monte Carlo simulations** to compare MILP against a "Greedy" Heuristic. Results show that while MILP is more efficient, the "Human Factor" (Switching Cost $\beta$) is crucial for real-world resilience.
