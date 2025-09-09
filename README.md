# Social Media vs Grades
*Analyzing Students’ Social Media Addiction and Academic Performance*

A reproducible, end‑to‑end data science pipeline exploring how student social‑media use relates to sleep, mental‑health, conflicts, and academic performance. The project demonstrates a full stack of techniques: **Pandas EDA**, **MRJob/MapReduce**, **Apache Spark (RDD/DataFrame/SQL)**, **graph analytics** (PageRank, triangle counting), and basic **spatial** modeling (Apache Sedona).

---

## Repository Structure 
```
.
├─ Students_Social_Media_Pipeline.ipynb   # End-to-end notebook (EDA → MRJob → Spark → Graph → Spatial)
├─ data/
│  └─ Students_Social_Media_Addiction.csv # Source dataset (kept locally; optionally ignored in Git)
├─ src/
│  ├─ mrjob_jobs/                         # MapReduce jobs
│  ├─ spark_jobs/                         # Spark RDD/DataFrame/SQL scripts
│  ├─ graph/                              # PageRank + triangle counting
│  └─ spatial/                            # Sedona: hulls, buffers, overlaps
├─ figures/                               # Generated plots/maps (ignored by default)
├─ requirements.txt
└─ README.md
```

## Environment Setup

### Option A — Python virtual environment (recommended)
```bash
python -m venv .venv

# Windows
.\.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Option B — Conda
```bash
conda create -n social-grades python=3.11 -y
conda activate social-grades
pip install -r requirements.txt
```

### Minimal `requirements.txt`
If you don’t have one yet, start with:
```
pandas
numpy
matplotlib
mrjob
pyspark
networkx
apache-sedona
geopandas
shapely
```
> You can generate an exact list from your environment with `pip freeze > requirements.txt`.

---

##  Quick Start

### Run the Notebook
Open **`Students_Social_Media_Pipeline.ipynb`** and execute cells top‑to‑bottom to:
- Load & clean data, engineer features (e.g., risk buckets)
- Compute platform usage summaries and correlations (MRJob/MapReduce)
- Run Spark RDD/DataFrame/SQL analysis
- Build a student–platform graph (PageRank, triangle counting)
- Generate basic spatial analytics (hulls, buffers, overlaps) with Sedona
- Output tables/figures into `figures/`

### (Optional) Run scripts from `src/`
```bash
# MRJob example
python src/mrjob_jobs/platform_stats.py data/Students_Social_Media_Addiction.csv

# Spark example
python src/spark_jobs/df_queries.py --input "data/Students_Social_Media_Addiction.csv" --out "figures/"

# Graph example (NetworkX or GraphFrames-based)
python src/graph/run_pagerank.py --input "data/Students_Social_Media_Addiction.csv"

# Spatial example (Sedona)
python src/spatial/hulls_and_buffers.py --input "data/Students_Social_Media_Addiction.csv" --epsg 3857
```

---

## Typical Outputs
- Per‑platform averages (usage hours, “addiction” score)
- Relationships between usage, sleep, mental‑health, and conflicts
- Graph metrics: platform influence (PageRank), clustering (triangle counts)
- Spatial coverage/overlap estimates for high‑risk vs global cohorts
- Reproducible figures saved to `figures/`

> Replace “addiction” with your dataset’s official field names; clarify scales (e.g., 0–10).

---

##  Reproducibility Tips
- Keep large CSVs in `data/` and add them to `.gitignore` (avoid storing raw PII in GitHub).
- Pin versions with `requirements.txt` or `conda env export`.
- Seed any random steps (`numpy.random.seed`, Spark `seed`) so charts/tables match your report.

---

##  Limitations
- Cross‑sectional, self‑reported data → **correlation, not causation**.
- Platform averages may reflect sample composition.
- Spatial areas are approximate for comparison, not precise geography.

---

##  Citation
If you use this repo, please cite the project as:
```
Nguyen, U., & Medepalli, S. (2025).
Social Media vs Grades: Analyzing Students’ Social Media Addiction and Academic Performance.
```
(Include your course/institution details if applicable.)

---
