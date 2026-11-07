# ICT Workers' Individual Issues — Country Cluster Analysis

A data analytics and unsupervised machine learning project exploring patterns in individual workplace issues among ICT workers across 37 countries using statistical analysis, clustering algorithms, and data visualization.

## Overview

This project investigates whether countries exhibit similar patterns in workplace-related issues experienced by ICT workers. It analyzes two sets of country-level scores (FS and S) across nine workplace attributes to identify similarities, differences, and potential country groupings.

The objective is not just to group countries, but also to evaluate whether meaningful cluster structures exist, compare clustering approaches, assess the stability of the results, and understand the differences between the two score sets.

## Dataset

The dataset contains observations from **37 countries**, with the following nine attributes:

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

### 1. Data Preprocessing

- Loaded and examined the original ICT dataset.
- Processed country-level measurements and prepared the FS and S score sets.
- Examined missing values, distributions, and descriptive statistics.
- Performed univariate and multivariate outlier analysis.
- Used Mahalanobis distance to identify potentially unusual country-level observations.
- Standardized the datasets to make the attributes comparable.

### 2. Exploratory Data Analysis

Conducted statistical exploration to understand the distribution and relationships between workplace attributes.

- Analyzed distributions of all nine attributes.
- Generated descriptive statistics.
- Examined correlations between attributes.
- Compared FS and S score distributions.
- Identified countries with substantial differences between the two score sets.

### 3. Clustering Analysis

Applied unsupervised learning techniques to identify groups of countries with similar workplace issue profiles.

**Algorithms used:**
- K-Means Clustering
- Hierarchical Agglomerative Clustering

**Techniques and evaluation metrics:**
- Hopkins Statistic — assessed clustering tendency.
- Elbow Method — examined within-cluster sum of squares.
- Silhouette Score — evaluated cluster separation.
- Calinski-Harabasz Index — measured cluster compactness and separation.
- Davies-Bouldin Index — evaluated cluster quality.
- Dunn Index — assessed inter-cluster separation relative to intra-cluster distances.
- Adjusted Rand Index (ARI) — measured agreement between clustering solutions.
- Cophenetic Correlation — evaluated hierarchical clustering representations.

The number of clusters was evaluated across multiple values of k, followed by comparisons between clustering algorithms and between FS and S datasets.

### 4. Cluster Validation and Robustness

To avoid relying solely on clustering scores:

- Compared observed silhouette scores against simulated datasets with no underlying cluster structure.
- Evaluated cluster stability using repeated subsampling.
- Compared K-Means and hierarchical clustering results.
- Examined agreement between FS and S cluster assignments.
- Evaluated individual country assignments using silhouette scores.
- Investigated how sensitive the clustering solutions were to different clustering configurations.

### 5. Data Visualization

Created visualizations to interpret the statistical and clustering results, including:

- Attribute distribution plots.
- Correlation heatmaps.
- Cluster evaluation plots.
- Elbow and silhouette analysis.
- Hierarchical clustering dendrograms.
- Country-level cluster visualizations.
- FS versus S comparison plots.

Visual outputs and exported analysis files are available in the `visuals/` directory.

## Key Findings

- The analysis identified a potential three-cluster structure across the countries.
- A two-cluster solution was more reproducible, while the three-cluster solution provided a finer grouping.
- The three-cluster solution showed some evidence of structure beyond what would be expected from simulated structureless data.
- The overall clustering evidence was relatively weak, highlighting the importance of validating unsupervised learning results rather than relying on a single metric.
- FS and S exhibited strong correlations across all nine workplace attributes, although certain countries showed notable differences between their standardized scores.

These findings demonstrate the importance of combining clustering algorithms with statistical validation and robustness analysis when interpreting country-level data.

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
├── clustering.ipynb
│   └── K-Means, hierarchical clustering and validation
│
└── visualization.ipynb
    └── Statistical comparisons and data visualizations
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

3. Create and activate a virtual environment (recommended):

```bash
python -m venv venv
```

On macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

4. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

5. Launch Jupyter Notebook:

```bash
jupyter notebook
```

### Running the Notebooks

Run the notebooks in the following order:

1. `preprocessing.ipynb` — prepares and processes the original dataset.
2. `clustering.ipynb` — performs clustering, evaluation, and validation.
3. `visualization.ipynb` — generates statistical comparisons and visual outputs.

Ensure the notebooks are executed from the repository's root directory so that relative file paths resolve correctly.

## Conclusion

This project demonstrates an end-to-end data analytics and unsupervised machine learning workflow, combining statistical preprocessing, exploratory data analysis, clustering, validation, and visualization.

Beyond identifying potential country groupings, the analysis emphasizes the importance of evaluating cluster reliability, comparing alternative models, and interpreting results cautiously when working with relatively small datasets.
