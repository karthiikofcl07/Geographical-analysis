# Geographic Analysis of Global Restaurant Distribution

**Cognifyz Technologies — Data Science Internship**
**Analyst: Karthikeyan Thirunavukkarasu**

---

## Overview

This project performs a rigorous geospatial analysis of a global restaurant dataset as part of the Cognifyz Technologies Data Science Internship. Using coordinate-based mapping, kernel density estimation, and DBSCAN spatial clustering, this analysis uncovers the geographic distribution patterns of over 9,500 restaurants across 15 countries and 141 cities.

The objective is twofold:

1. **Visualize** restaurant locations on a global coordinate map using longitude and latitude
2. **Identify** spatial clusters and density patterns to derive location intelligence insights

---

## Project Structure

```
cognifyz_geographic_analysis/
├── geographic_analysis.ipynb     # Main Jupyter notebook (full analysis)
├── cognifyz_dataset.csv          # Source dataset
├── fig1_global_map.png           # Global scatter map (rating-colored)
├── fig2_density_heatmap.png      # KDE density heatmap — global + India zoom
├── fig3_dbscan_clusters.png      # DBSCAN spatial clustering map
├── fig4_city_bubble_map.png      # City-level bubble map
├── fig5_quadrant_analysis.png    # 4-panel: bar, scatter, rating, pie charts
├── fig6_marginal_distributions.png  # Latitude and longitude frequency profiles
├── fig7_cluster_heatmap.png      # Cluster quality heatmap matrix
└── README.md                     # This document
```

---

## Dataset

| Attribute         | Value         |
|-------------------|---------------|
| Total Records     | 9,551         |
| Features          | 21            |
| Countries         | 15            |
| Cities            | 141           |
| Latitude Range    | -41.33° to 55.98° |
| Longitude Range   | -157.95° to 174.83° |
| Missing Geo Data  | 0             |

---

## Analytical Methodology

### 1. Global Coordinate Mapping
All restaurant records are plotted as scatter points on a Cartesian coordinate grid representing the globe. Points are colored by `Aggregate rating` using a diverging colormap from red (low) to green (high), revealing both distribution and quality patterns geographically.

### 2. Kernel Density Estimation (KDE)
A 2D Gaussian KDE (`scipy.stats.gaussian_kde`) is applied over longitude-latitude space to produce smooth density surfaces. Two resolutions are rendered — global and a zoomed view of the South Asia / NCR corridor — allowing both macro and micro-level pattern detection.

### 3. DBSCAN Spatial Clustering
Density-Based Spatial Clustering of Applications with Noise (DBSCAN) is applied using Haversine distance on radian-converted coordinates. Parameters: `eps = 0.3 degrees (~33 km)`, `min_samples = 15`. This method detects clusters of arbitrary shape without requiring a predefined cluster count, and isolates geographic outliers explicitly as noise.

### 4. City-Level Bubble Map
Each city is represented as a bubble whose **size encodes restaurant count** and **color encodes average rating**. This dual-encoding enables simultaneous comparison of market density and quality concentration across cities.

### 5. Marginal Distribution Analysis
Independent histograms with KDE overlays for both latitude and longitude expose the axial skew of the dataset — confirming the Northern Hemisphere, 20°–35°N latitude band as the dominant zone.

---

## Key Findings

**Geographic Concentration**
India accounts for approximately 90.6% of the dataset, with the National Capital Region (New Delhi, Gurgaon, Noida, Faridabad) hosting over 7,900 restaurants — more than 83% of all records.

**DBSCAN Clustering**
The algorithm detected multiple statistically significant spatial clusters. The largest cluster centers on New Delhi with over 5,000 restaurants. Approximately 3.2% of restaurants are classified as geographic outliers scattered outside major metropolitan zones.

**Latitudinal Bias**
The dataset's median latitude is approximately 28.57°N, with the interquartile range between 28.48°N and 28.64°N — an exceptionally tight band corresponding to the NCR corridor, reflecting the dataset's strong regional bias.

**International Clusters**
Beyond South Asia, identifiable secondary clusters exist in the United States (New York, Chicago), UAE (Dubai, Abu Dhabi), United Kingdom (London), South Africa (Cape Town, Johannesburg), and the Philippines (Metro Manila) — though these represent minor fractions relative to the Indian core.

**Quality vs. Geography**
Northern Hemisphere restaurants in the subtropical band (23.5°N–45°N) exhibit the widest rating variance, while restaurants in the Southern Hemisphere and tropical zones show slightly more concentrated rating distributions around the 3.0–4.0 range.

---

## Visualizations Produced

| Figure | Description |
|--------|-------------|
| `fig1_global_map.png` | Global scatter plot of all restaurants, colored by aggregate rating |
| `fig2_density_heatmap.png` | KDE density surface — global and South Asia regional zoom |
| `fig3_dbscan_clusters.png` | Spatial cluster assignments from DBSCAN, annotated with top cluster metadata |
| `fig4_city_bubble_map.png` | City-level bubble map encoding count (size) and average rating (color) |
| `fig5_quadrant_analysis.png` | Four-panel: city bar chart, zone scatter, rating bars, country pie chart |
| `fig6_marginal_distributions.png` | Frequency distribution profiles for latitude and longitude |
| `fig7_cluster_heatmap.png` | Normalized quality matrix for the top 15 DBSCAN clusters |

---

## Setup & Execution

### Requirements

```
Python >= 3.8
jupyter
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

### Installation

```bash
pip install jupyter pandas numpy matplotlib seaborn scikit-learn scipy
```

### Run

```bash
cd cognifyz_geographic_analysis
jupyter notebook geographic_analysis.ipynb
```

Execute all cells sequentially (Kernel > Restart & Run All). All output figures are saved automatically as PNG files to the project directory.

---

## Technologies Used

- **Python 3** — Core language
- **Pandas** — Data ingestion and wrangling
- **NumPy** — Numerical operations
- **Matplotlib** — Primary visualization engine
- **Seaborn** — Statistical heatmap rendering
- **scikit-learn** — DBSCAN clustering (Haversine metric)
- **SciPy** — Gaussian KDE, convex hull computation
- **Jupyter Notebook** — Interactive analysis environment

---

## About the Analyst

**Karthikeyan Thirunavukkarasu**
Data Science Intern — Cognifyz Technologies

LinkedIn: [linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305](https://www.linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305)
GitHub: [github.com/karthiikofcl07](https://github.com/karthiikofcl07)

---

*This project was completed as part of a structured internship program at Cognifyz Technologies. All analysis, code, and visualizations are original work produced by the analyst.*
