# 🍺 Beer & GIS

Geospatial analysis through the lens of craft beer — exploring GIS concepts, spatial methods, and the Pacific Northwest brewing landscape.

**Live site:** [brooksgroves.com/beer-gis](https://brooksgroves.com/beer-gis) *(coming soon)*

---

## What's in here

### GIS Concepts — Explained with Beer
Five core GIS topics, each illustrated with Pacific Northwest brewery scenarios:

| Concept | Beer Example |
|---|---|
| [Raster Operations](gisp-concepts/raster-ops.html) | Hop yard suitability analysis — Local, Focal, Zonal, Global |
| [Overlay Operations](gisp-concepts/overlay-ops.html) | Taproom siting — Union, Intersect, Clip, Erase |
| [Classification Methods](gisp-concepts/classification.html) | Brewery ratings map — Natural Breaks, Quantile, Equal Interval, Std Dev |
| [Data Quality](gisp-concepts/data-quality.html) | PNW brewery dataset — Positional, Logical, Attribute, Temporal |
| [Visual Variables](gisp-concepts/visual-variables.html) | Beer tourism map — Value, Hue, Size, Shape, Texture, Orientation |

### Pacific Northwest Brewery Atlas
A full geospatial analysis project covering:
- Spatial distribution and KDE hotspot analysis
- Proximity to Yakima Valley hop-growing regions
- Taproom siting using overlay analysis
- Rating geography and classification method comparison
- Delivery route optimization via network analysis

---

## Stack
- Static HTML / CSS — no frameworks
- Python + GeoPandas + Folium (analysis notebooks coming soon)
- Data: OpenStreetMap, USDA, US Census Bureau TIGER/Line

---

## About
Built by [Brooks Groves](https://brooksgroves.com) — GIS Analyst & Data Scientist, Lakewood WA.  
Originally developed as a study companion for the GISP certification exam.

---

*Because the best way to remember that Kernel Density Estimation produces a smooth hotspot surface from point data is to picture 400 brewery locations dissolving into a heat map of where the good beer is.*
