
# Brewery Supply Chain Optimization

## 📊 Project Overview

This project addresses a complex distribution planning challenge for a UK-based brewing company. Using **Linear Programming (LP)**, I developed a mathematical model to minimize total transportation costs across a multi-tier supply chain.

The network consists of:

* 
**4 Breweries** (Production) 


* 
**3 Packaging Facilities** (Intermediate Processing) 


* 
**15 Demand Locations** (Retailers and Pubs) 



## 🛠️ Tech Stack

* 
**Language:** Python 3.x 


* 
**Optimization Library:** [PuLP](https://coin-or.github.io/pulp/) 


* 
**Analytics Platform:** KNIME Analytics Platform (Integrated via Python Source Node) 



## 🎯 Key Objectives

1. 
**Minimize Logistics Costs:** Optimize shipping plans across the distribution network to achieve the lowest possible expenditure while satisfying all constraints.


2. 
**Facility Viability Analysis:** Evaluate the utilization of breweries and packaging facilities to identify candidates for closure based on minimum operational thresholds.


3. 
**Scenario Planning:** Conduct "what-if" analyses by adjusting demand levels to identify system bottlenecks and capacity breaking points.



## 📈 Insights & Results

### **1. Cost Optimization**

The model successfully identified an optimal shipping strategy resulting in a **minimum total transportation cost of $2,359**.

### **2. Underutilization & Recommendations**

By comparing actual output against minimum capacity requirements, the following insights were uncovered:

* 
**Brewery 2 and Brewery 4** are the primary candidates for consolidation or closure, as both operate at their exact minimum required production levels (150 and 100 units, respectively).


* All **Packaging Facilities** are operating significantly above their minimum capacity thresholds, indicating they are essential to current operations.



### **3. Capacity Bottlenecks**

Through the use of an incremental `demand_multiplier`, the analysis revealed:

* The system's primary constraint is **Total Packaging Capacity** ( units).


* The model becomes **infeasible** at a demand multiplier of 5, as demand ( units) exceeds the combined output of all packaging centers.



| Demand Multiplier | Total Demand | Total Shipping Costs | Status |
| --- | --- | --- | --- |
| 1 | 949 | $2,359 | Optimal 

 |
| 2 | 1,898 | $4,642 | Optimal 

 |
| 3 | 2,847 | $6,942 | Optimal 

 |
| 4 | 3,796 | $9,251 | Optimal 

 |
| 5 | 4,745 | (N/A) | <br>**Infeasible** 

 |

## 📂 Project Structure

```text
├── src/
│   └── run-brewery-v000.py       # Main Python optimization logic
├── results/
│   └── workflow.svg              # Visual representation of the KNIME workflow
├── docs/
│   └── Brewery_distribution.pdf   # Comprehensive business analysis report
└── README.md                     # Project summary and documentation

```

## 🚀 How to Run

1. **Clone the Repo:**



2. **Install Dependencies:**
```bash
pip install pulp

```


3. **Execute:** Run the script in the `src/` folder. Modify the `demand_multiplier` variable to perform your own scenario testing.

