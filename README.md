# SCI030: Exploring, Documenting & Visualising Public Space Data

A summer research repository documenting public NASA and space-related data sources (APIs, bulk downloads, and web-scrapable portals), cross-dataset linking strategies, ethical scraping guidelines, and interactive R visualisations.

*While the code is MIT-licensed, the underlying NASA, Wikimedia, and third-party datasets remain subject to their respective source attribution and terms.*

## Table of Contents

- [Dataset & Source Catalogue](#dataset--source-catalogue)
- [NASA Meteorite Landings](#nasa-meteorite-landings)
  - [Dataset Summary](#dataset-summary)
  - [Variable Dictionary](#variable-dictionary)
- [Planetary Alignment & Eclipse Visualiser](#planetary-alignment--eclipse-visualiser)

---

## Dataset & Source Catalogue

*Under Construction.*

---

## NASA Meteorite Landings

**Source:** [NASA Open Data Portal: Meteorite Landings](https://data.nasa.gov/dataset/meteorite-landings) (compiled from The Meteoritical Society)  
**Planned Output:** Interactive global hexbin heatmap with separate land ("fire") and ocean ("hydro") colour scales, an ordinal chronological slider with photo-availability markers, and a detail panel enriched with country/region lookups and Wikimedia Commons thumbnails.

### Dataset Summary

- **Record Count:** The original portal description notes 34,513 records prior to a May 14, 2013 update; the current CSV contains **45,716 rows** across **10 variables**.
- **Temporal Range & Anomalies:** Records span from **860 CE** (the historic *Nogata* fall in Japan; not a typo) through **2013**. One anomalous entry lists the year **2101** (*Northwest Africa 7701*), a known human data-entry typo in the source table that must be filtered or corrected during cleaning.
- **Coordinate Quirks:** Several rows contain missing coordinates (`NA`) or placeholder `(0.000000, 0.000000)` values (off the coast of West Africa) that must be removed before spatial mapping.

### Variable Dictionary

| Variable | Type | Description & Categorical Values |
| :--- | :--- | :--- |
| `name` | Character | Official name of the meteorite, typically derived from the geographic location where it was recovered (e.g., *Aachen*, *Abee*). |
| `id` | Integer | Unique numeric identifier assigned by The Meteoritical Society. |
| `nametype` | Categorical | Indicates whether the entry is a standard classification (**`Valid`**) or a weathered/altered specimen (**`Relict`**) that no longer retains its original mineral composition. |
| `recclass` | Character | Petrologic/chemical classification of the meteorite based on composition and structure (e.g., `L5`, `H6`, `EH4` chondrites; iron; stony-iron). |
| `mass (g)` | Numeric | Total recovered mass of the meteorite in grams. Highly right-skewed (ranging from sub-gram fragments to the 60-tonne *Hoba* meteorite). |
| `fall` | Categorical | Discovery circumstance: **`Fell`** means the meteorite was witnessed falling to Earth before recovery; **`Found`** means it was discovered later without an observed fall. |
| `year` | Integer | Year the meteorite was observed falling (`Fell`) or discovered (`Found`). |
| `reclat` | Numeric | Latitude of the landing/recovery site in decimal degrees (WGS84). |
| `reclong` | Numeric | Longitude of the landing/recovery site in decimal degrees (WGS84). |
| `GeoLocation` | Character | Combined `(reclat, reclong)` coordinate string formatted for quick spatial indexing. |

---

## Planetary Alignment & Eclipse Visualiser

*Under Construction*

