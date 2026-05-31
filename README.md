# Baby Name Visualisations in France (1900–2020)

Interactive data visualisations of French baby names from 1900 to 2020, built with **Altair** and **GeoPandas**. This project is the Week 2 submission for the Data Visualisation course.

---

## Dataset

Source: [INSEE](https://www.insee.fr) — French civil registry baby names, aggregated by department.

| File | Description |
|---|---|
| `dpt2020.csv` | ~3.7 M rows — name, year, department, sex, count |
| `departements-version-simplifiee.geojson` | Simplified department boundaries (metropolitan France) |
| `departements-avec-outre-mer.geojson` | Department boundaries including overseas territories |

Columns in `dpt2020.csv`: `sexe` (1 = male, 2 = female), `preusuel` (first name), `annais` (year), `dpt` (department code), `nombre` (birth count).

---

## Visualisations

### Visualisation 1 — Temporal Evolution
> *How do baby names evolve over time? Are there names that have consistently remained popular? Are there trends over time?*

An interactive **line chart** showing the 20 most popular names from 1900 to 2020.  
Click a name in the legend to highlight its trajectory (all others fade out).

### Visualisation 2 — Regional Effect
> *Are some names more popular in certain regions? Are popular names generally popular across the whole country?*

An interactive **choropleth map** of metropolitan France.  
A dropdown lets you select any of the top 60 names; the colour encodes births **per 1,000 births** in each department (normalised to remove population-size bias).

### Visualisation 3 — Gender Effects
> *Are there gender effects in the data? Does the popularity of names given to both sexes evolve consistently?*

An interactive **stacked 100% area chart** showing the male/female breakdown of a name over time.  
Only unisex names (given to both sexes at more than 5%) appear in the dropdown. A dashed line at 50% makes gender switches easy to spot.

---

## Setup

This project uses [Poetry](https://python-poetry.org/) for dependency management (Python 3.12).

### 1. Install dependencies

```bash
git clone https://github.com/omar7878/visualisation-prenoms.git
cd visualisation-prenoms
poetry install
```

### 2. Register the Jupyter kernel

```bash
poetry run python -m ipykernel install --user \
  --name="visualisation-prenoms" \
  --display-name="Python (visualisation-prenoms)"
```

### 3. Open the notebook

Open `visualisations_prenoms.ipynb` in VS Code (or JupyterLab), select the **Python (visualisation-prenoms)** kernel, and run all cells.

---

## Dependencies

| Package | Purpose |
|---|---|
| `altair` | Interactive charts and maps |
| `pandas` | Data wrangling |
| `geopandas` | GeoJSON loading and spatial merges |
| `ipykernel` | Jupyter kernel registration |
| `jupyter` | Notebook environment |

---

## Project structure

```
.
├── visualisations_prenoms.ipynb   # Main notebook (3 visualisations)
├── dpt2020.csv                    # INSEE baby names dataset
├── departements-version-simplifiee.geojson
├── departements-avec-outre-mer.geojson
├── pyproject.toml                 # Poetry project file
└── README.md
```
