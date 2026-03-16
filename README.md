<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=220&section=header&text=Geographic%20Analysis&fontSize=50&fontColor=ffffff&fontAlignY=38&desc=Global%20Restaurant%20Distribution%20%7C%20Cognifyz%20Technologies&descAlignY=58&descSize=17&animation=fadeIn" width="100%"/>

</div>

<div align="center">

# Karthikeyan Thirunavukkarasu

### Data Science Intern — Cognifyz Technologies

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/karthiikofcl07)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)](https://matplotlib.org)

</div>

---

## Table of Contents

- [Project Overview](#project-overview)
- [Internship Context](#internship-context)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Analytical Methodology](#analytical-methodology)
- [Code Walkthrough](#code-walkthrough)
- [Visualizations Produced](#visualizations-produced)
- [Key Findings](#key-findings)
- [Technologies & Libraries](#technologies--libraries)
- [Setup & Execution](#setup--execution)
- [About the Analyst](#about-the-analyst)

---

## Project Overview

This project delivers a comprehensive **geospatial analysis** of a global restaurant dataset, fulfilling the Geographic Analysis task assigned as part of the Cognifyz Technologies Data Science Internship.

The analysis addresses two core requirements:

1. **Plot** the locations of all restaurants on a global coordinate map using longitude and latitude
2. **Identify** spatial patterns, density hotspots, and geographic clusters of restaurant concentration

To meet these requirements at a professional standard, the project deploys a multi-method analytical pipeline — from raw coordinate mapping and kernel density estimation through to algorithmic spatial clustering — producing seven publication-quality visualizations and a structured findings report rendered as rich Markdown within the notebook.

---

## Internship Context

| Attribute    | Details                                 |
|--------------|-----------------------------------------|
| Organization | Cognifyz Technologies                   |
| Domain       | Data Science & Analytics                |
| Task         | Geographic Analysis                     |
| Analyst      | Karthikeyan Thirunavukkarasu            |
| Deliverable  | Jupyter Notebook + Exported PNG Figures |

---

## Dataset Description

The source file `cognifyz_dataset.csv` contains restaurant records aggregated from Zomato's platform, spanning multiple countries and cities.

| Attribute                | Value                  |
|--------------------------|------------------------|
| Total Records            | 9,551                  |
| Records After Geo Filter | 9,052                  |
| Features                 | 21                     |
| Countries                | 15                     |
| Cities                   | 141                    |
| Latitude Range           | −41.33° to +55.98°     |
| Longitude Range          | −157.95° to +174.83°   |
| Missing Coordinates      | 0                      |

### Feature Reference

| Column                 | Type    | Description                                     |
|------------------------|---------|-------------------------------------------------|
| `Restaurant ID`        | Integer | Unique identifier for each establishment        |
| `Restaurant Name`      | String  | Trading name of the restaurant                  |
| `Country Code`         | Integer | Numeric code mapped to country name             |
| `City`                 | String  | City where the restaurant operates              |
| `Address`              | String  | Full street address                             |
| `Locality`             | String  | Neighbourhood or locality name                  |
| `Longitude`            | Float   | WGS84 longitude coordinate                      |
| `Latitude`             | Float   | WGS84 latitude coordinate                       |
| `Cuisines`             | String  | Comma-separated cuisine types served            |
| `Average Cost for two` | Integer | Average spend for two diners (local currency)   |
| `Currency`             | String  | Local currency name                             |
| `Has Table booking`    | Boolean | Whether advance table reservation is available  |
| `Has Online delivery`  | Boolean | Whether the restaurant offers online delivery   |
| `Price range`          | Integer | Price tier from 1 (budget) to 4 (premium)       |
| `Aggregate rating`     | Float   | Overall rating score (0.0 – 5.0)                |
| `Rating color`         | String  | Categorical label corresponding to rating band  |
| `Rating text`          | String  | Textual rating descriptor                       |
| `Votes`                | Integer | Total number of user votes received             |

---

## Project Structure

```
cognifyz_geographic_analysis/
│
├── geographic_analysis.ipynb        # Main analysis notebook (11 sections)
├── cognifyz_dataset.csv             # Source dataset
│
├── fig1_global_map.png              # Global scatter map — rating-colored
├── fig2_density_heatmap.png         # KDE heatmap — global + India zoom
├── fig3_dbscan_clusters.png         # DBSCAN spatial cluster map
├── fig4_city_bubble_map.png         # City bubble map (count × rating)
├── fig5_quadrant_analysis.png       # 4-panel deep-dive visualization
├── fig6_marginal_distributions.png  # Latitude & longitude frequency profiles
├── fig7_cluster_heatmap.png         # Cluster quality matrix heatmap
│
├── README.md                        # This document
├── INTRO.md                         # Styled introduction page
└── CONCLUSION.md                    # Structured conclusion page
```

---

## Analytical Methodology

The notebook is organized into eleven sequential sections, each building on the previous to produce a progressively deeper understanding of the geographic data.

### Section 1 — Project Overview
A styled HTML/Markdown introduction cell establishing context: internship organization, task definition, analyst identity, and analytical scope. Uses inline CSS for dark-theme gradient styling consistent with the visualization aesthetic.

### Section 2 — Environment Setup & Library Imports
All dependencies are imported and a **global aesthetic configuration** is applied via `plt.rcParams`. A custom dark-theme color palette (`PALETTE` dictionary) is defined and used consistently across all seven figures to maintain visual coherence throughout the analysis.

### Section 3 — Data Ingestion & Quality Assessment
The dataset is loaded with `pandas.read_csv`. A structured quality report is printed covering total records, feature count, geographic extent, and missing value counts. Records with zero-value coordinates (mapping artifacts) are filtered out before analysis proceeds. Descriptive statistics for coordinate and rating columns are printed as a reference baseline.

### Section 4 — Global Restaurant Distribution Map *(Figure 1)*
All restaurants are plotted as scatter points on a Cartesian longitude-latitude grid. Points are colored using a continuous diverging colormap mapped to `Aggregate rating`, allowing simultaneous inspection of both spatial distribution and quality. Reference lines mark the equator, prime meridian, and tropic lines. A bounding box annotation highlights the dominant India cluster. A colorbar provides quantitative rating reference.

### Section 5 — Density Heatmap *(Figure 2)*
A 2D **Kernel Density Estimation** is computed using `scipy.stats.gaussian_kde` over the longitude-latitude space. Two panels are rendered side-by-side:
- **Global KDE** — full-world density surface using a 400×300 evaluation grid with 40 contour levels
- **South Asia Zoom** — high-resolution view of the NCR corridor with annotated city markers for New Delhi, Gurgaon, Noida, and Mumbai

### Section 6 — DBSCAN Spatial Clustering *(Figure 3)*
**DBSCAN** (`sklearn.cluster.DBSCAN`) is applied with Haversine distance on radian-converted coordinates. Configuration: `eps = 0.3` (≈33 km), `min_samples = 15`. The algorithm identifies clusters of arbitrary shape and explicitly labels geographic outliers as noise (label = −1). Cluster metadata — count, average rating, average votes, centroid coordinates, and dominant city — is aggregated and printed as a ranked summary table before the figure is rendered.

### Section 7 — City-Level Geographic Analysis *(Figure 4)*
Each city is aggregated to compute total restaurant count, average rating, and average votes. The top 30 cities are rendered as a **bubble map** where bubble size encodes restaurant count and bubble color encodes average rating, enabling dual-dimensional reading from a single visual mark. The top 10 cities are annotated directly on the map. A size legend provides quantitative reference.

### Section 8 — Rating Distribution Across Geographic Zones *(Figure 5)*
A four-panel figure using `GridSpec` layout provides a multi-dimensional breakdown:
- **Panel A** — Horizontal bar chart of top 20 cities by restaurant count with tier-based color coding
- **Panel B** — Scatter plot of rating vs. votes with points colored by latitudinal zone (Southern / Tropical / Subtropical / Northern), using symlog y-scale to handle vote count skew
- **Panel C** — Average rating bar chart for the top 15 cities, colored by RdYlGn colormap with a 3.5-star threshold reference line
- **Panel D** — Pie chart of restaurant share by country for the top 10 nations

### Section 9 — Longitude & Latitude Distribution Profiles *(Figure 6)*
Independent frequency histograms (120 bins) for both latitude and longitude, each overlaid with a KDE curve and vertical reference lines for median and mean. This side-by-side layout directly exposes the extreme axial skew of the dataset and allows the distributions' shapes to be compared at a glance.

### Section 10 — Cluster Quality & Summary Statistics *(Figure 7)*
The top 15 DBSCAN clusters are evaluated across three metrics: restaurant count, average rating, and average votes. Values are min-max normalized per column and rendered as a **Seaborn heatmap** with raw values annotated inside each cell. This enables rapid identification of clusters that are simultaneously large, high-rated, and highly engaged.

### Section 11 — Key Findings Report
All computed metrics are assembled into a **richly formatted Markdown findings report** rendered via `IPython.display.Markdown`. Six structured findings cover dataset scope, India dominance, DBSCAN results, latitudinal bias, rating geography, and international market distribution — each with inline computed statistics, formatted tables, and a modelling implication callout.

---

## Code Walkthrough

### Global Theme Configuration

```python
PALETTE = {
    'bg':      '#0f0f1a',
    'panel':   '#1a1a2e',
    'accent1': '#e94560',
    'gold':    '#f5a623',
    'teal':    '#00b4d8',
    'text':    '#ccd6f6',
    'muted':   '#8892b0',
}

plt.rcParams.update({
    'figure.facecolor': PALETTE['bg'],
    'axes.facecolor':   PALETTE['panel'],
    'axes.labelcolor':  PALETTE['text'],
    'text.color':       PALETTE['text'],
    'grid.color':       '#2a2a4a',
    ...
})
```

A single dictionary drives all color decisions across every figure, ensuring visual consistency and making theme adjustments a single-point change across the entire analysis.

---

### Data Quality Filter

```python
df_geo = df[(df['Latitude'] != 0) & (df['Longitude'] != 0)].copy()
```

Records with zero-value coordinates are artifacts of missing geo-data encoded as zero rather than null. Filtering these before any spatial analysis prevents false cluster formation at the geographic origin (0°, 0° — Gulf of Guinea), which would corrupt both KDE and DBSCAN outputs.

---

### KDE Density Surface

```python
kde = gaussian_kde(np.vstack([lons, lats]), bw_method=0.08)
lon_grid = np.linspace(-180, 180, 400)
lat_grid = np.linspace(-60, 75, 300)
LON, LAT = np.meshgrid(lon_grid, lat_grid)
Z = kde(np.vstack([LON.ravel(), LAT.ravel()])).reshape(LON.shape)
ax.contourf(LON, LAT, Z, levels=40, cmap=heat_cmap)
```

The bandwidth `bw_method=0.08` is tuned to balance global visibility with local resolution. A 400×300 evaluation grid provides sufficient detail without excessive computation. The `contourf` call with 40 levels produces a smooth, gradient-like surface rather than a stepped appearance.

---

### DBSCAN with Haversine Distance

```python
coords_rad = np.radians(df_geo[['Latitude', 'Longitude']].values)
db = DBSCAN(eps=0.3, min_samples=15, metric='haversine').fit(coords_rad)
df_geo['cluster'] = db.labels_
```

Coordinates are converted to radians before fitting because scikit-learn's Haversine implementation expects radian inputs. The `eps` value of `0.3` radians corresponds to approximately 33 km on Earth's surface — a reasonable urban density zone radius. `min_samples=15` ensures that only genuine metropolitan concentrations qualify as clusters.

---

### Cluster Statistics Aggregation

```python
cluster_stats = (
    df_geo[df_geo['cluster'] != -1]
    .groupby('cluster')
    .agg(
        count      = ('Restaurant ID', 'count'),
        avg_rating = ('Aggregate rating', 'mean'),
        avg_votes  = ('Votes', 'mean'),
        center_lat = ('Latitude', 'mean'),
        center_lon = ('Longitude', 'mean'),
        top_city   = ('City', lambda x: x.mode()[0])
    )
    .sort_values('count', ascending=False)
    .reset_index()
)
```

Noise points (label = −1) are excluded before aggregation. The `top_city` field uses `mode()[0]` to assign the most frequently occurring city name within each cluster — a robust proxy for the cluster's geographic identity that handles multi-city clusters gracefully.

---

### Dual-Encoded Bubble Map

```python
sc2 = ax.scatter(
    top_cities['lon'], top_cities['lat'],
    s          = top_cities['count'] / 5,   # size  → restaurant count
    c          = top_cities['avg_rating'],   # color → average rating
    cmap       = cmap_r,
    norm       = norm_r,
    alpha      = 0.9,
    edgecolors = 'white',
    linewidths = 0.5
)
```

Dual encoding (size × color) allows two independent quantitative dimensions to be read from a single mark without visual confusion, following established cartographic best practice for proportional symbol maps.

---

### Markdown Findings Renderer

```python
md = f"""
## Key Findings & Analytical Insights
...
| Country | Restaurants | Share of Dataset |
|---------|-------------|-----------------|
{intl_table_rows}
...
"""
from IPython.display import Markdown, display
display(Markdown(md))
```

Rather than plain `print()` output, findings are rendered as styled Markdown inside the notebook — producing formatted headings, bold emphasis, tables, and blockquotes that match the professional standard of the visualizations. All values are injected via f-string interpolation from live computed variables, so the report is always accurate regardless of dataset changes.

---

## Visualizations Produced

| Figure | Filename                         | Technique                  | Key Insight Delivered                            |
|--------|----------------------------------|----------------------------|--------------------------------------------------|
| 1      | `fig1_global_map.png`            | Scatter plot, continuous colormap | Global distribution + rating quality by location |
| 2      | `fig2_density_heatmap.png`       | 2D Gaussian KDE, contourf  | Density hotspots + NCR corridor detail           |
| 3      | `fig3_dbscan_clusters.png`       | DBSCAN, Haversine metric   | Algorithmically defined spatial clusters         |
| 4      | `fig4_city_bubble_map.png`       | Dual-encoded bubble map    | City count vs. quality side-by-side comparison   |
| 5      | `fig5_quadrant_analysis.png`     | GridSpec 4-panel           | Multi-dimensional city and country breakdown     |
| 6      | `fig6_marginal_distributions.png`| Histogram + KDE overlay    | Axial skew of the geographic distribution        |
| 7      | `fig7_cluster_heatmap.png`       | Normalized heatmap (Seaborn) | Cluster quality matrix across 3 metrics         |

All figures are saved at **150 DPI** with `bbox_inches='tight'` and a consistent dark background (`facecolor = '#0f0f1a'`).

---

## Key Findings

**1. Geographic Concentration**
India accounts for 90.1% of all dataset restaurants. The NCR corridor — New Delhi, Gurgaon, Noida, and Faridabad — alone contributes 7,525 restaurants, representing 83.1% of the entire global dataset.

**2. DBSCAN Clustering**
Multiple statistically significant spatial clusters were detected. The largest cluster, centered on New Delhi, contains over 5,000 restaurants. Approximately 3.2% of records are geographic outliers existing outside any metropolitan density zone.

**3. Extreme Latitudinal Skew**
The dataset's interquartile latitude range spans less than 0.15 degrees — roughly 17 km — confirming that 50% of all records exist within a single city-region corridor in northern India.

**4. Quality Distribution**
The global average aggregate rating is 2.73 / 5.0. Only 12.0% of restaurants achieve a rating above 4.0. Bangalore leads major cities in average votes per restaurant, indicating stronger review engagement than the NCR average despite lower restaurant density.

**5. International Markets**
The United States (434 restaurants), United Kingdom (80), Brazil (60), UAE (60), and South Africa (60) form the primary international clusters — each representing less than 5% of India's restaurant count in the dataset.

**6. Modelling Implication**
Any predictive model trained on this dataset will predominantly reflect Indian urban dining patterns. Generalisation to international markets requires explicit reweighting or stratified sampling strategies to avoid systematic bias.

---

## Technologies & Libraries

| Library      | Purpose                                              |
|--------------|------------------------------------------------------|
| Python 3.8+  | Core language                                        |
| pandas       | Data ingestion, wrangling, groupby aggregation       |
| NumPy        | Numerical operations, meshgrid generation, radians   |
| Matplotlib   | Primary visualization engine for all 7 figures       |
| Seaborn      | Statistical heatmap rendering (Figure 7)             |
| scikit-learn | DBSCAN spatial clustering with Haversine metric      |
| SciPy        | Gaussian KDE, statistical distribution utilities     |
| IPython      | Markdown rendering inside Jupyter notebook cells     |
| Jupyter      | Interactive analysis and execution environment       |

---

## Setup & Execution

### 1. Clone or Extract the Project

```bash
# Clone from GitHub
git clone https://github.com/karthiikofcl07/cognifyz-geographic-analysis.git
cd cognifyz-geographic-analysis

# Or extract the zip and navigate into the folder
cd cognifyz_geographic_analysis
```

### 2. Install Dependencies

```bash
pip install jupyter pandas numpy matplotlib seaborn scikit-learn scipy ipython
```

### 3. Launch the Notebook

```bash
jupyter notebook geographic_analysis.ipynb
```

Or open the folder in VS Code, select the notebook file, and choose **Run All** from the top toolbar with a Python kernel active.

### 4. Expected Output

All seven figures will render inline within the notebook and be saved as PNG files to the project directory automatically at the end of their respective cells.

### requirements.txt

```
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
ipython
jupyter
```

---

## About the Analyst

| | |
|---|---|
| **Name** | Karthikeyan Thirunavukkarasu |
| **Role** | Data Science Intern — Cognifyz Technologies |
| **LinkedIn** | [linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305](https://www.linkedin.com/in/karthikeyan-thirunavukkarasu-2a2949305) |
| **GitHub** | [github.com/karthiikofcl07](https://github.com/karthiikofcl07) |

---

<div align="center">

*This project was completed as part of a structured internship program at Cognifyz Technologies.*
*All analysis, code, visualizations, and documentation are original work produced by the analyst.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>

</div>
