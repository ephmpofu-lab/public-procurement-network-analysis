# Applied Network Analysis and Causal Machine Learning

This repository contains two applied data science projects demonstrating how different analytical methods answer fundamentally different types of questions.

The first project uses network analysis to examine relationships between contracting authorities and winning companies in Austrian public procurement.

The second project uses Double Machine Learning to estimate the causal effect of 401(k) eligibility on household net financial assets.

---

## Project 1 — Austrian Public Procurement Network Analysis

### Problem

Public procurement data are typically stored as transactional records. While these records show individual contract awards, they do not immediately reveal the wider structure of relationships between contracting authorities and suppliers.

Understanding this structure can help identify highly connected organisations, recurring procurement relationships, influential actors, and clusters of organisations that interact more frequently with each other.

### Research Question

**What structural patterns, influential actors, and communities emerge from relationships between contracting authorities and winning companies in Austrian public procurement data?**

### Approach

The analysis:

- cleans and standardises contracting authority and company names;
- constructs a directed authority-to-company network;
- aggregates repeated procurement relationships;
- calculates network centrality measures;
- applies PageRank to identify structurally prominent organisations;
- detects network communities using the Louvain algorithm;
- creates static and interactive network visualisations.

### Network Structure

The network is represented as:

**Contracting Authority → Winning Company**

Each node represents an organisation.

Each edge represents a procurement relationship between a contracting authority and a winning company.

Edge attributes include:

- number of awards;
- total procurement value.

### Tools

- Python
- pandas
- NetworkX
- Matplotlib
- PyVis
- Louvain community detection

### Outputs

The project produces:

- a cleaned procurement network;
- centrality and PageRank rankings;
- detected procurement communities;
- an interactive HTML network visualisation;
- an exported network edge list.

---

## Project 2 — Causal Machine Learning: 401(k) Eligibility and Financial Assets

### Problem

A simple comparison of financial assets between households that are eligible and not eligible for a 401(k) plan does not necessarily identify a causal effect.

Households differ in income, age, education, family structure, pension arrangements, and other observed characteristics. These differences may influence both 401(k) eligibility and accumulated financial assets.

The analytical challenge is therefore to estimate the effect of 401(k) eligibility while accounting for observed differences between households.

### Research Question

**What is the estimated causal effect of 401(k) eligibility on household net financial assets?**

### Approach

The project applies Double Machine Learning using:

- a binary treatment variable: 401(k) eligibility (`e401`);
- an outcome variable: net total financial assets (`net_tfa`);
- observed household characteristics as control variables;
- Random Forest models for nuisance-function estimation;
- cross-fitting to reduce overfitting bias;
- an Interactive Regression Model implemented with DoubleML.

### Result

The model estimated an average treatment effect of approximately:

**$8,039**

with a 95% confidence interval of approximately:

**$5,833 to $10,245**

Under the identification assumptions of the model, the results indicate a positive estimated effect of 401(k) eligibility on net financial assets.

### Tools

- Python
- DoubleML
- scikit-learn
- Random Forest
- pandas
- Matplotlib

---

## Repository Structure

    public-procurement-network-analysis/
    │
    ├── Notebooks/
    │   ├── 01_explore_data.ipynb
    │   └── 02_causal_analysis.ipynb
    │
    ├── procurement_network_edges.csv
    ├── procurement_network_interactive.html
    ├── export_CAN_2022.csv
    ├── .gitignore
    └── README.md

---

## Analytical Perspective

These projects demonstrate two complementary analytical perspectives.

**Network analysis** asks:

> How are actors connected, which organisations are structurally important, and what communities emerge?

**Causal machine learning** asks:

> What is the estimated effect of an intervention or treatment on an outcome?

Together, the projects demonstrate the ability to move beyond descriptive analysis toward relational and causal analytical methods.

---

## Author

Dr. Ephraim Mpofu
