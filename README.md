# Circle Drawing and Tracing — Speed-Accuracy Analysis
### Python-R-Git Project | Master STAPS | 2025-2026

## Author
**Tuba Tuba**  
Master in Engineering and Ergonomics of Physical Activity  
Course: Python-R-Git | Supervisor: Denis MOTTET  
GitHub Repository: https://github.com/tuba1079/tuba.tuba

---

## Scientific Question
In healthy adults performing circular hand movements, does faster 
execution come at the cost of reduced trajectory accuracy, and does 
this speed-accuracy tradeoff differ between internally guided 
(drawing) and externally guided (tracing) conditions?

**Hypothesis:** Drawing will show faster movement times but higher 
trajectory deviation than tracing, confirming a speed-accuracy 
tradeoff modulated by external visual guidance.


## Dataset
- **Source:** Quarta et al. (2021), *Data in Brief*, 
  https://doi.org/10.1016/j.dib.2021.106763
- **Participants:** 125 healthy adults (23.6 ± 5 years, 114 females)
- **Tasks:** Circle drawing (internal guidance) vs circle tracing 
  (external guidance)
- **Format:** 250 CSV files — columns: x, y, time
- **Sampling rate:** ~50 Hz

## Analysis Pipeline

### Python (main.ipynb)
- Load and parse all 250 CSV files
- Smooth trajectories (Savitzky-Golay filter)
- Compute movement time (MT) per subject per task
- Fit circle → compute RMSE (accuracy measure)
- Compute tangential velocity profiles
- Visualize trajectories, velocity, MT and RMSE distributions

### R (main.Rmd)
- Descriptive statistics (mean, SD, median) per task
- Normality check (QQ plots + Shapiro-Wilk test)
- Wilcoxon signed-rank test: MT drawing vs tracing
- Wilcoxon signed-rank test: RMSE drawing vs tracing
- Correlation test: MT vs RMSE per task
- Box plots of MT and RMSE

---

## Requirements

### Python
- pandas
- numpy
- scipy
- matplotlib
- seaborn

### R
- ggplot2
- dplyr
- tidyr

---

## Branches
| Branch | Purpose |
|---|---|
| `main` | Final clean version |
| `data-exploration` | First look at the data |
| `python-analysis` | All Python/Jupyter work |
| `r-analysis` | All R/RMarkdown work |
| `report` | HTML report |

---
## Project Structure
```
tuba.tuba/
|── README.md
|── LICENSE
|── data/          → raw CSV files (subset for testing)
|── results/       → output figures and statistics
|── notebooks/     → Jupyter and Rmd notebooks (optional)
|── sources/       → reusable Python and R functions
|── main.ipynb     → entry point: all Python analyses
|── main.Rmd       → entry point: all R analyses
|── main.Rproj     → RStudio project file

```

## License
MIT License — see LICENSE file

