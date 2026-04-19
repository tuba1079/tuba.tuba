# Circle Drawing and Tracing — Motor Control Analysis
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
- Load and parse all CSV files
- Smooth trajectories using Savitzky–Golay filtering
- Compute movement time per subject and task
- Compute RMSE as a trajectory-accuracy metric
- Compute time-normalized velocity profiles
- Generate trajectory and kinematic visualizations

### R (main.Rmd)
- Descriptive statistics (mean, SD, median) per task
- Normality check (QQ plots + Shapiro-Wilk test)
- Wilcoxon signed-rank test: MT drawing vs tracing
- Wilcoxon signed-rank test: RMSE drawing vs tracing
- Robustness Analysis: Perform paired t-tests
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
- tidyverse
- ggplot2
- dplyr
- tidyr
- broom
- rstatix
- effsize
- ggpubr
- patchwork
- kableExtra

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
├── README.md
├── LICENSE
├── main.ipynb
├── main.Rmd
├── main.Rproj
├── Tuba_Tuba.html
├── data/
│   └── (raw CSV files used for testing)
├── results/
│   ├── main_results.csv
│   ├── figure1.png
│   ├── figure2.png
│   ├── figure3.png
│   ├── figure4.png
│   ├── boxplots-1.png
│   ├── download.png
│   ├── movement_time_boxplot.png
│   ├── rmse_boxplot.png
│   ├── speed_accuracy_tradeoff.png
│   ├── subject-profiles-1.png
│   ├── trajectories.png
│   ├── velocity_average.png
│   ├── velocity_normalized_average.png
│   ├── velocity_normalized_individual.png
│   ├── velocity_normalized.png
│   └── velocity_profiles.png
├── notebooks/
│   └── (notebook copies)
└── sources/
    └── (optional reusable functions)

```

## License
MIT License — see LICENSE file

