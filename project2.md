---
layout: page
title: Portfolio Optimization
---
**Optimization** is the process of finding the best solution to a problem from a set of possible solutions. It involves selecting the values of certain variables (**decision variables**) to either:

- **Maximize** something desirable (e.g., profit, efficiency, or happiness), and/or  
- **Minimize** something undesirable (e.g., cost, time, or waste),  

while satisfying certain **constraints** (rules or limits) imposed by the problem.

## Visualizing the Efficient Frontier

To better understand the efficient frontier, here's an interactive chart:


<!-- EMBED THE HTML CHART -->
<style>
iframe {
    border: none;
    box-shadow: none;
}
</style>
<iframe src="/public/charts/1.html" width="100%" height="600px"></iframe>
<!-- END EMBEDDING THE HTML CHART -->

Let’s apply optimization to a financial portfolio. The goal is to adjust a mix of investments (e.g., stocks or other securities) to meet specific objectives and constraints. Tools like **Aladdin** can help investors set up this problem by defining:

- **Objective function (goals)**  
- **Constraints (rules)**  

The tool then finds the **optimal mix of investments** that satisfies all the requirements.

---

## Example 1: Minimizing Portfolio Risk ##

Imagine you currently own a mix of three stocks. Your goal is to adjust how much money you have invested in each stock (by buying more or selling some) to reduce the overall risk of your portfolio. At the same time, you need to make sure of two things:

1. All your money stays invested—no leftover cash. In other words, you are **fully invested**.
2. You can’t borrow stocks to sell them; you can only sell what you already own. In other words, you are **no shorting**.

| **Stock** | **Current Weight** | **New Weight** | **Risk/Volatility** | **Sector**   |
|-----------|--------------------|----------------|---------------------|--------------|
| A         | 20%               | x₁            | 20                  | Technology   |
| B         | 30%               | x₂            | 30                  | Energy       |
| C         | 50%               | x₃            | 40                  | Energy       |

- **Current Weight** represents your initial allocation to each stock.  
- **New Weights** `x₁, x₂, x₃` represent the new proportions of your budget invested in Stocks A, B, and C **after** optimizing.

The objective is to **minimize portfolio risk**, expressed as:

`Z(x) = 20x₁ + 30x₂ + 40x₃`

### Constraints

1. **Fully Invested**:  
   100% of the available capital must be allocated.  
   `x₁ + x₂ + x₃ = 1`

2. **No Shorting**:  
   This is a long-only portfolio, in other words, there can be no negative positions.  
   `x₁, x₂, x₃ ≥ 0`

### Optimal Solution

When this optimization problem is solved, the **optimal solution** is to allocate 100% of the portfolio to **Stock A**, as this is the stock with the lowest risk. This satisfies the objective of minimizing portfolio risk under the given constraints.

---

## Example 2: Minimizing Risk While Maximizing ESG Scores ##

Building on the first example, let’s now introduce a second objective: **maximizing ESG (Environmental, Social, and Governance) scores**, which measure the sustainability and ethical impact of an investment.

The new objective is to balance minimizing portfolio risk with maximizing ESG scores. The problem setup remains the same, with the following additions:

| **Stock** | **Current Weight** | **New Weight** | **ESG Score** | **Risk/Volatility** | **Sector**   |
|-----------|--------------------|----------------|---------------|---------------------|--------------|
| A         | 20%               | x₁            | 10            | 20                  | Technology   |
| B         | 30%               | x₂            | 15            | 30                  | Energy       |
| C         | 50%               | x₃            | 20            | 40                  | Energy       |

### Dual Objective Optimization Problem

To balance the two objectives, we define a **weighted objective function**:

`Z(x) = w₁ * (20x₁ + 30x₂ + 40x₃) - w₂ * (10x₁ + 15x₂ + 20x₃)`

Where:  
- `w₁` and `w₂` are weights that reflect the importance of minimizing risk and maximizing ESG scores, respectively.
- The first term represents portfolio risk (to minimize).
- The second term represents ESG scores (to maximize).

### Constraints

1. **Fully Invested**:  
   100% of the available capital must be allocated.  
   `x₁ + x₂ + x₃ = 1`

2. **No Shorting**:  
   This is a long-only portfolio, in other words, there can be no negative positions.  
   `x₁, x₂, x₃ ≥ 0`

### Weights and Priority

The weights `w₁` and `w₂` allow the investor to decide which objective takes priority:
- If `w₁` > `w₂`, the model prioritizes minimizing risk.
- If `w₂` > `w₁`, the model prioritizes maximizing ESG scores.

The optimal portfolio allocation will depend on the chosen weights, reflecting the investor's preferences.

---

## Efficient Frontier

The **efficient frontier** is a concept in portfolio optimization that represents the set of optimal portfolios offering the best possible trade-off between competing objectives, such as risk and ESG scores.  

Each point on the efficient frontier corresponds to a portfolio that:
1. Minimizes risk for a given level of ESG score, or
2. Maximizes ESG score for a given level of risk.

Portfolios below the efficient frontier are suboptimal because either a higher ESG score could be achieved for the same risk, or lower risk could be achieved for the same ESG score. By varying the weights `w₁` and `w₂`, the optimization process identifies portfolios along the efficient frontier, allowing investors to select the portfolio that best aligns with their goals.

---
