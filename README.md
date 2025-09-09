# Social Media vs Grades  
*Analyzing Students’ Social Media Addiction and Academic Performance*

A small, reproducible data-science project exploring how student social-media use relates to sleep, mental health, conflicts, and academic performance. The repo contains one Jupyter notebook, one Python script, one CSV dataset, and a PDF analysis/report.

> **Study type:** correlational (not causal).  
> **Data care:** avoid sharing PII; publish only aggregated results.

---

## Repository Structure
```
README.md
Students_Social_Media_Pipeline.ipynb
Students_Social_Media_pipeline.py
Students Social Media Addiction.csv
Analyzing Students Social Media Addiction and Academic Performance.pdf
```

---

## Environment Setup

```bash
python -m venv .venv

# Windows PowerShell
.\.venv\Scripts\Activate.ps1
# Windows CMD
.\.venv\Scripts\activate.bat
# macOS/Linux
source .venv/bin/activate

python -m pip install --upgrade pip
```

### Install the minimal libraries you need
```bash
pip install pandas numpy matplotlib
```
> Add others only if you use them:
> - MapReduce: `pip install mrjob`
> - Spark: `pip install pyspark`
> - Graph: `pip install networkx`
> - Spatial: `pip install apache-sedona geopandas shapely` (advanced)

---

## Quick Start

### Run the notebook
Open **`Students_Social_Media_Pipeline.ipynb`** and execute cells top-to-bottom.

### Run the Python script
```bash
python Students_Social_Media_pipeline.py
```

---

## Typical Outputs
- Per-platform summaries (usage hours, “addiction” score)  
- Relationships between usage, sleep, mental-health, conflicts  
- Figures saved locally (if the notebook/script generates them)

---

## Limitations
- Cross-sectional, self-reported data → **correlation, not causation**.  
- Platform averages may reflect sample composition.  
- Any spatial numbers (if used) are approximate for comparison, not precise geography.

---

## Citation
If you use this repo, please cite:
```
Nguyen, U., & Medepalli, S. (2025).
Social Media vs Grades: Analyzing Students’ Social Media Addiction and Academic Performance.
```
