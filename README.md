# Supply‑Chain Optimization Model & Scenario Simulation

This repository contains all code, documentation, and reports for a linear‑programming model that optimises a five‑country manufacturing network (USA, Germany, Japan, Brazil, India).  
The work was produced for the course **“Introduction to Business Analytics”** (Foreign Trade University, 2024‑2025) and demonstrates how cost‑minimising factory‑location decisions can be stress‑tested under demand uncertainty.

---

## Objective
* Select factory locations / capacities and product flows that minimise cost  
  *(fixed + variable production + freight)*
* Explore trade‑offs between cost and unmet demand penalties
* Quantify network robustness via 50 Monte‑Carlo demand scenarios and compare alternative footprints

---

## Tools & Techniques
| Area | Details |
|------|---------|
| Optimisation | **PuLP** linear programming solver; binary plant‑opening and continuous flow variables; capacity, demand and logical constraints |
| Simulation | **NumPy / SciPy** truncated‑normal demand generator (CV = 0.5) feeding repeated solves |
| Data Wrangling | **Pandas** DataFrames for cost inputs, scenario matrices, and result tables |
| Visualisation | **Matplotlib / Seaborn / Plotly** for cost breakdowns, Sankey flow, utilisation charts, heat‑maps of factory choices |
| Reporting | Jupyter Notebook (`Code.ipynb`) and accompanying report (`Report.pdf`) |

---

## Key Deliverables
| Deliverable | Highlight |
|-------|---------|
| **Optimal (INITIAL) footprint** | 4 plants – USA‑High‑capacity, Japan‑High, India‑High, Brazil‑Low – at **\$92.98 M / month**. |
| **Brazil viability** | Brazil‑L worthwhile only if the penalty for not meeting demand ≥ 1.2 × average variable cost. |
| **Scenario results** | 22 unique footprints; top two: INITIAL (20 %) and C2 (14 %). C9 rejected after capacity check. |
| **INITIAL vs C2** | INITIAL wins in **43 / 50** scenarios (cheaper & feasible). C2 wins 40 / 50 (cheaper) but has more infeasible runs. |
| **Takeaway** | Slight cost savings are outweighed by higher failure risk; INITIAL chosen as final solution. |

---

## Repository Structure
```
.
├── Code.ipynb                        # End-to-end modelling & simulation notebook
├── Report.pdf                        # 60-page technical report with figures & discussion
├── Requirements.pdf                  # Project brief / problem statement
├── Supply chain optimization_data/   # Folder containing input Excel data
│   ├── capacity.xlsx
│   ├── demand.xlsx
│   ├── fixed_cost.xlsx
│   ├── freight_costs.xlsx
│   ├── total_costs.xlsx
│   └── variable_costs.xlsx
└── README.md                         # (this file)
```
---

## How to Use

1. **Set up your environment**  
   Ensure Python is installed, along with the following libraries:

   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scipy`
   - `plotly`
   - `pulp`
   - `os` (built-in)
   - `google.colab` (if running in Google Colab)

2. **Open the notebook**  
   Launch Jupyter Notebook or a compatible environment, and open: `Code.ipynb`

3. **Load the data**  
   The notebook uses input files from the `Supply chain optimization_data/` folder. Make sure all Excel files are present.

4. **Run the notebook**  
   Execute each cell sequentially to:  
   - Load and process the data  
   - Apply optimization models  
   - Generate visualizations and outputs

5. **View the report**  
   See `Report.pdf` for detailed explanations and results.
   
> ⚠️ **Disclaimer**  
> The author shaped the optimisation logic and business assumptions, but he is **NOT** an advanced Python programmer.  
> Most of the code was produced with AI assistance and then checked against the model’s intent. Syntax was frequently looked up as needed.
> This repository is a proof‑of‑concept to demonstrate analytical reasoning only.

---

## 👤 Contact

**Trương Bảo Khang**  
Email: truongbaokhang.work@gmail.com  
University: Foreign Trade University  
Major: International Economics  
