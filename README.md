# ICT Workers' Individual Issues — Country Cluster Analysis

An exploratory data analysis and unsupervised machine learning project investigating patterns in individual workplace issues among ICT workers across 37 countries using statistical analysis, clustering algorithms, and data visualization.

## Overview

This project explores whether countries exhibit similar patterns in workplace-related issues experienced by ICT workers. It analyzes two sets of country-level scores (FS and S) across nine workplace attributes to identify similarities, differences, and potential country groupings.

The objective is to identify meaningful patterns in the data, compare clustering approaches, assess the stability of clustering solutions, and understand the differences between the two score sets.

## Dataset

The dataset contains observations from **37 countries**, with nine workplace-related attributes:

| Code | Attribute |
|---|---|
| FC | Friendship Circles |
| JI | Job Insecurity |
| SE | Self-Efficacy |
| WS | Work Satisfaction |
| WO | Work Overload |
| WH | Work-Home Conflict |
| WE | Work Exhaustion |
| TI | Turnover Intention |
| TA | Turnaway Intention |

Each attribute has two corresponding measurements:
- **FS:** First set of country-level scores.
- **S:** Second set of country-level scores.

The dataset also includes the number of respondents per country.

## Project Workflow

The project is organized into three main stages, executed sequentially.

### 1. Data Preprocessing

- Loaded and examined the original ICT dataset.
- Processed country-level measurements and prepared the FS and S score sets.
- Examined missing values and descriptive statistics.
- Performed univariate and multivariate outlier analysis.
- Used Mahalanobis distance to identify potentially unusual country-level observations.
- Standardized the datasets to make attributes comparable.

### 2. Data Visualization and Exploratory Data Analysis

Conducted exploratory analysis to understand the distributions, relationships, and patterns within the workplace attributes.

- Analyzed distributions of all nine attributes.
- Generated descriptive statistics.
- Examined correlations between workplace attributes.
- Compared FS and S score distributions.
- Identified countries with notable differences between the two score sets.
- Generated statistical plots and correlation heatmaps.

### 3. Clustering and Analysis

Applied unsupervised machine learning techniques to identify groups of countries with similar workplace issue profiles.

**Clustering algorithms:**
- K-Means Clustering
- Hierarchical Agglomerative Clustering

**Evaluation and validation techniques:**
- Hopkins Statistic — assessed clustering tendency.
- Elbow Method — examined within-cluster sum of squares.
- Silhouette Score — evaluated cluster separation.
- Calinski-Harabasz Index — measured cluster compactness and separation.
- Davies-Bouldin Index — evaluated cluster quality.
- Dunn Index — assessed inter-cluster separation relative to intra-cluster distances.
- Adjusted Rand Index (ARI) — measured agreement between clustering solutions.
- Cophenetic Correlation — evaluated hierarchical clustering representations.

**Robustness analysis:**
- Compared clustering solutions across different values of k.
- Compared K-Means and hierarchical clustering results.
- Evaluated cluster stability using repeated subsampling.
- Compared FS and S cluster assignments.
- Examined individual country assignments using silhouette scores.
- Compared observed clustering results against simulated datasets without underlying cluster structure.

## Key Findings

- The analysis identified a potential three-cluster structure across the countries.
- A two-cluster solution was more reproducible, while the three-cluster solution provided a finer grouping.
- The three-cluster solution showed some evidence of structure beyond what would be expected from simulated structureless data.
- Overall clustering evidence was relatively weak, highlighting the importance of validating unsupervised learning results rather than relying on a single metric.
- FS and S exhibited strong correlations across all nine workplace attributes, although certain countries showed notable differences between their standardized scores.

These findings emphasize the importance of combining clustering algorithms with statistical validation and robustness analysis when interpreting country-level data.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Data analysis and implementation |
| Pandas | Data manipulation and preprocessing |
| NumPy | Numerical computations |
| Scikit-learn | Clustering, standardization, and evaluation |
| SciPy | Statistical analysis and hierarchical clustering |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Jupyter Notebook | Interactive analysis and experimentation |

## Repository Structure

```text
mp3-Country-Cluster-Analysis/
│
├── visuals/
│   └── Generated plots and analysis outputs
│
├── ICTIndiv.xlsx
│   └── Original dataset
│
├── ICT_preprocessed.csv
│   └── Preprocessed country-level dataset
│
├── preprocessing.ipynb
│   └── Data cleaning, preprocessing and outlier analysis
│
├── visualization.ipynb
│   └── Exploratory data analysis and visualizations
│
├── clustering.ipynb
│   └── Clustering algorithms, evaluation and validation
│
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.9+
- Jupyter Notebook

### Installation

1. Clone the repository:

```bash
git clone https://github.com/navya2006/mp3-Country-Cluster-Analysis.git
```

2. Navigate to the project directory:

```bash
cd mp3-Country-Cluster-Analysis
```

3. Create a virtual environment:

```bash
python -m venv venv
```

Activate it:

**macOS/Linux**
```bash
source venv/bin/activate
```

**Windows**
```bash
venv\Scripts\activate
```

4. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter openpyxl
```

5. Launch Jupyter Notebook:

```bash
jupyter notebook
```

### Running the Notebooks

Execute the notebooks in the following order:

**1. `preprocessing.ipynb`**

Cleans the original dataset, processes country-level scores, performs missing-value and outlier analysis, and prepares the data for further analysis.

**2. `visualization.ipynb`**

Performs exploratory data analysis (EDA), examines attribute distributions and correlations, compares FS and S measurements, and generates visualizations to understand patterns in the dataset.

**3. `clustering.ipynb`**

Applies K-Means and Hierarchical Clustering, evaluates optimal cluster configurations, performs cluster validation and stability analysis, and interprets the resulting country groups.

Ensure the notebooks are executed from the repository's root directory so that relative file paths resolve correctly.

## Conclusion

This project demonstrates an end-to-end data analytics and unsupervised machine learning workflow, combining statistical preprocessing, exploratory data analysis, clustering, validation, and visualization.

Beyond identifying potential country groupings, the analysis emphasizes the importance of evaluating cluster reliability, comparing alternative models, and interpreting results cautiously when working with relatively small datasets.
