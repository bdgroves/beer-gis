# 🍺 Beer & GIS — Pacific Northwest Brewery Geospatial Analysis

> *A geospatial data science project exploring craft brewery distribution, market geography, and spatial analytics across the Pacific Northwest — anchored by Fort George Brewery in Astoria, Oregon.*

**Brooks Groves** · GIS Analyst & Data Scientist · Lakewood, WA  
[brooksgroves.com](https://brooksgroves.com) · [LinkedIn](https://linkedin.com/in/brooksgroves)

---

## Overview

This project applies professional GIS and spatial data science methods to the Pacific Northwest craft brewing landscape. Starting with Fort George Brewery — a 34,000 barrel/year operation at the mouth of the Columbia River — the analysis scales outward to examine the full regional brewing ecosystem across Oregon, Washington, and Idaho.

The project serves two purposes: a rigorous spatial analysis portfolio piece, and a practical demonstration of GIS concepts through real-world industry data.

**Fort George Brewery** — founded 2007 at 1483 Duane Street, Astoria, Oregon — sits at the geographic intersection of several compelling spatial questions: it operates at the edge of the continent, within a day's drive of the Willamette Valley hop farms, and distributes across four states through a road network constrained by the Coast Range and Columbia River geography. It's an ideal anchor for regional distribution analysis, proximity modeling, and market geography work.

---

## Project Structure

```
beer-gis/
├── index.html                    # Project landing page
├── brewery-analysis/
│   └── index.html               # PNW Brewery Atlas overview
├── gisp-concepts/
│   ├── raster-ops.html          # Local/Focal/Zonal/Global
│   ├── overlay-ops.html         # Union/Intersect/Clip/Erase
│   ├── classification.html      # Natural Breaks/Quantile/Std Dev
│   ├── data-quality.html        # ISO 19157 quality elements
│   └── visual-variables.html    # Bertin's semiology
├── analysis/                    # Python notebooks (coming)
│   ├── 01_spatial_distribution.ipynb
│   ├── 02_hop_proximity.ipynb
│   ├── 03_taproom_siting.ipynb
│   ├── 04_distribution_network.ipynb
│   └── 05_market_geography.ipynb
├── data/                        # Raw and processed datasets (coming)
└── README.md
```

---

## Analysis Modules

### Module 1 — Spatial Distribution & Density
**Question:** Where are PNW craft breweries concentrated, and how does Fort George's location in Astoria compare to regional clusters?

- Kernel Density Estimation (KDE) of ~1,200 PNW brewery locations
- Choropleth mapping of brewery density per 100,000 residents by county
- Hot spot analysis (Getis-Ord Gi*) identifying statistically significant clusters
- Fort George positioned relative to the Portland metro, Willamette Valley, and coast clusters

**Methods:** KDE, Zonal Statistics, Spatial Autocorrelation  
**Tools:** Python · GeoPandas · PySAL · Folium

---

### Module 2 — Hop Growing Region Proximity
**Question:** How does Fort George's position on the North Oregon Coast relate to Pacific Northwest hop-growing geography?

- Euclidean and network distance from every PNW brewery to the Willamette Valley and Yakima Valley hop-growing regions
- The Yakima Valley (WA) produces ~75% of US hops — drive time from Astoria: ~4.5 hours
- Hop availability surface across the PNW using cost distance raster analysis
- Fort George's position relative to freshness-focused "harvest ale" production windows

**Methods:** Cost Distance (Global raster), Network Analysis, Drive-time Polygons  
**Tools:** Python · OSMnx · NetworkX · GeoPandas

---

### Module 3 — Distribution Network Analysis
**Question:** What is the optimal distribution territory for a 34,000 bbl/year brewery operating from Astoria?

- Drive-time catchment areas at 1, 2, 3, and 4 hour intervals from Fort George
- Least-cost path routing through the Coast Range road network
- Population coverage analysis — how many residents are within each catchment zone?
- Competitive overlap analysis: which distribution zones have the highest brewery density?
- Fort George's four-state distribution footprint (OR, WA, ID, N. California) mapped against road network constraints

**Methods:** Network Analysis, Drive-time Polygons, Least-Cost Path, Spatial Join  
**Tools:** Python · OSMnx · NetworkX · GeoPandas · Folium

---

### Module 4 — Taproom & Event Geography
**Question:** What spatial factors explain why Fort George's Festival of Dark Arts draws attendees from across the Pacific Northwest to Astoria each February?

- Origin geography of festival attendees (anonymized travel shed analysis)
- Drive-time gravity model: how far do people travel for a destination beer event?
- Astoria's position at the Columbia River mouth as a geographic attractor
- Competing event analysis: which other PNW beer festivals compete for the same geography?

**Methods:** Gravity Modeling, Drive-time Analysis, Spatial Join  
**Tools:** Python · GeoPandas · Shapely

---

### Module 5 — Market Geography & Retail Coverage
**Question:** How is Fort George beer distributed across retail accounts, and where are the coverage gaps?

- Retail account density mapping across the four-state distribution footprint
- Underserved market identification using population-weighted coverage analysis
- Competitor shelf-space analysis by sub-region
- Optimal new market entry geography using weighted spatial scoring

**Methods:** Spatial Join, Weighted Overlay, Market Area Analysis  
**Tools:** Python · GeoPandas · PySAL · Folium

---

### Module 6 — Brewing Geography Over Time
**Question:** How has the PNW craft brewing landscape changed since Fort George opened in 2007?

- Temporal animation of brewery openings 2007–2024 across the PNW
- Market saturation analysis by county — breweries per capita over time
- Fort George's market position trajectory as regional competition increased
- Identification of underserved markets based on population/brewery ratios

**Methods:** Temporal Analysis, Choropleth Mapping, Change Detection  
**Tools:** Python · GeoPandas · Matplotlib · Folium

---

## GIS Concepts Reference

The `gisp-concepts/` directory contains illustrated explainers for core GIS methods — each demonstrated through brewery data scenarios:

| Concept | Brewery Application |
|---|---|
| [Raster Operations](gisp-concepts/raster-ops.html) | Hop yard suitability — Local, Focal, Zonal, Global |
| [Overlay Operations](gisp-concepts/overlay-ops.html) | Taproom siting — Union, Intersect, Clip, Erase |
| [Classification Methods](gisp-concepts/classification.html) | Rating maps — Natural Breaks, Quantile, Std Dev |
| [Data Quality](gisp-concepts/data-quality.html) | Brewery dataset QA — ISO 19157 elements |
| [Visual Variables](gisp-concepts/visual-variables.html) | Tourism map design — Bertin's semiology |

---

## Data Sources

| Dataset | Source | Notes |
|---|---|---|
| Brewery locations & attributes | OpenStreetMap + Brewers Association | ~1,200 PNW locations |
| Hop growing regions | USDA NASS | Yakima Valley, Willamette Valley extents |
| County boundaries | US Census Bureau TIGER/Line | OR, WA, ID, N. CA |
| Road network | OpenStreetMap via OSMnx | Full routable network |
| Population data | US Census Bureau ACS 5-Year | County and tract level |
| Retail accounts | Proprietary / simulated | Anonymized for analysis |
| Fort George locations | Direct / OSM | Duane St pub + waterfront production brewery |

---

## Environment Setup

This project uses [pixi](https://pixi.sh) for Python environment management.

```bash
# Clone the repo
git clone https://github.com/bdgroves/beer-gis.git
cd beer-gis

# Install pixi if needed
curl -fsSL https://pixi.sh/install.sh | bash

# Create environment and install dependencies
pixi install

# Launch Jupyter
pixi run jupyter lab
```

**Core dependencies:** `geopandas` · `osmnx` · `networkx` · `pysal` · `folium` · `matplotlib` · `shapely` · `rasterio` · `jupyter`

---

## Roadmap

- [x] Project structure and landing page
- [x] GIS concept explainers (all 5 topics)
- [x] Brewery Atlas project outline
- [ ] Module 1: KDE and density analysis (Python notebook)
- [ ] Module 2: Hop proximity analysis
- [ ] Module 3: Distribution network analysis
- [ ] Module 4: Festival of Dark Arts travel shed
- [ ] Module 5: Retail market geography
- [ ] Module 6: Temporal brewing landscape analysis
- [ ] Interactive Folium maps deployed to GitHub Pages
- [ ] pixi.toml environment configuration

---

## About

Built by [Brooks Groves](https://brooksgroves.com), GIS Analyst and Data Scientist at Zillow in Lakewood, WA. Published work in *Cartographic Perspectives*. Projects include [ALPINE-WATCH](https://brooksgroves.com/Alpine-watch) (Sierra Nevada and Cascade lake water quality monitoring) and AFTERSHOCK (real-time seismic visualization for the Pacific Northwest).

Fort George Brewery is a personal favorite — the 3 Way IPA is exceptional, the Festival of Dark Arts is one of the great Pacific Northwest winter traditions, and Astoria is the kind of place that makes you want to make maps.

---

*"Nobody is ever 'in the neighborhood' of Astoria unless they're on a fishing trawler or on the lam from the feds."*  
— The Pour Fool

---

**Live site:** [bdgroves.github.io/beer-gis](https://bdgroves.github.io/beer-gis)
