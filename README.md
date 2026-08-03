# Degradation-Aware Optimal Sizing Framework for Grid-Interactive EV Charging Stations

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

## Paper

**Title:** Degradation-Aware Optimal Sizing Framework for Grid-Interactive EV Charging
Stations with PV, BESS, and Supercapacitor: Real Dataset Validation Using
NASA PCoE, ACN-Data, and CHARGED

**Authors:** Kingsuk Majumdar, Sohini Ghosh, Nishant Kumar, Indrani Ghosh

**Journal:** Modern Power Systems and Clean Energy (MPCE),
IEEE/SGEPRI, Diamond Open Access, IF 6.3, Q1

**Status:** Under Review (August 2026)

**DOI (paper):** To be assigned upon acceptance

---

## Repository Contents

This repository contains all numerical results, statistical validation data,
sensitivity analysis outputs, and publication figures supporting the paper.
Simulation pipeline scripts are available from the corresponding author
upon reasonable request (kingsuk.majumdar@bcrec.ac.in).

```
2026-07-11_J07__NASA_EV_SC/
|
+-- README.md                          <- This file 
|
+-- OUTPUT/
|   |
|   +-- S03/                           <- Main optimisation results
|   |   +-- S03_R01_main_results_table_full.csv
|   |   |     Optimal sizing (PV, BESS, SC) and TAC for all 4 cases
|   |   |     and 4 algorithms (Table IV in paper)
|   |   +-- S03_R02_convergence_case1.csv
|   |   +-- S03_R02_convergence_case2.csv
|   |   +-- S03_R02_convergence_case3.csv
|   |   +-- S03_R02_convergence_case4.csv
|   |   |     Best TAC per iteration (0-500) for each algorithm
|   |   |     (used for convergence figures and AUC analysis)
|   |   +-- S03_R03_gwo_best_solutions.json
|   |   |     GWO best solution details for all 4 cases
|   |   +-- S03_R04_tac_comparison_all_cases.csv
|   |   |     TAC summary across all algorithms and cases
|   |   +-- S03_REPORT_summary_full.txt
|   |   |     Full text summary of S03 results
|   |   +-- S03_results_progress_full.json
|   |       Complete optimisation progress checkpoint (all 16 runs)
|   |
|   +-- S05/                           <- CHARGED generalisation results
|   |   +-- S05_R01_charged_city_results.csv
|   |       GWO Case 4 optimal sizing for Amsterdam, Los Angeles,
|   |       Sao Paulo (Table V in paper)
|   |
|   +-- S06/                           <- Convergence quality metrics
|   |   +-- S06_R01_auc_analysis.csv
|   |   |     Normalised AUC (mean excess above final TAC) per case
|   |   |     and algorithm (Table VI in paper)
|   |   +-- S06_R02_convergence_speed.csv
|   |   |     Iterations to reach within 1% of final TAC per case
|   |   +-- S06_R03_combined_summary.csv
|   |   |     Combined AUC and speed summary
|   |   +-- S06_R04_latex_table.tex
|   |       LaTeX source for Table VI (algorithm performance)
|   |
|   +-- S07/                           <- Sensitivity analysis
|   |   +-- S07_R01_alpha_sensitivity.csv
|   |   |     TAC and BESS SoH for alpha_comm +/-30% (Table VII in paper)
|   |   +-- S07_R02_kp_sensitivity.csv
|   |   |     TAC and grid cost for kp = 2.0, 2.5, 3.0, 3.5 (Table VIII)
|   |   +-- S07_R03_economic_sensitivity.csv
|   |   |     TAC for +/-20% variation in PV capex, BESS capex,
|   |   |     demand charge, and discount rate (tornado chart)
|   |   +-- S07_R04_alpha_table.tex
|   |   |     LaTeX source for Table VII
|   |   +-- S07_R05_kp_table.tex
|   |   |     LaTeX source for Table VIII
|   |   +-- S07_REPORT_sensitivity_summary.txt
|   |       Full sensitivity analysis report
|   |
|   +-- S08/                           <- 30-run statistical validation
|       +-- S08_R01_summary_statistics.csv
|       |     Mean, SD, best, worst, CV, Friedman rank for 30 runs
|       |     per algorithm (Table IX in paper)
|       +-- S08_R02_wilcoxon_results.csv
|       |     Wilcoxon signed-rank test results (GWO vs BBO, AO, ARO)
|       +-- S08_R03_nemenyi_results.csv
|       |     Nemenyi post-hoc pairwise rank differences vs CD
|       +-- S08_R04_friedman_summary.csv
|       |     Friedman chi-square, p-value, and mean ranks
|       +-- S08_R05_sc_consistency.csv
|       |     SC module count distribution across 30 runs per algorithm
|       +-- S08_R06_latex_table.tex
|       |     LaTeX source for Table IX
|       +-- S08_progress.json
|       |     Raw TAC values for all 120 runs (30 seeds x 4 algorithms)
|       |     Seeds: 1000-1029, N_iter=100, N_pop=15
|       +-- S08_REPORT.txt
|           Complete statistical validation report with paper text
|
+-- FIGURES/                           <- All publication figures (PDF, 18 files)
    +-- S04_fig01_soh_degradation.pdf
    |     NASA PCoE capacity fade trajectories (Fig. 1)
    +-- S04_fig02_ev_load_profile.pdf
    |     ACN-Data EV load profile, JPL Arroyo Garage (Fig. 2)
    +-- S04_fig03_pv_generation.pdf
    |     PVGIS-ERA5 PV generation profile, JPL Pasadena (Fig. 3)
    +-- S04_fig04_convergence_case4.pdf
    |     Algorithm convergence curves, Case 4 (Fig. 4)
    +-- S04_fig05_tac_decomposition.pdf
    |     TAC decomposition, GWO-optimal solutions (Fig. 5)
    +-- S04_fig06_bess_degradation.pdf
    |     BESS cycle count and SoH, Cases 2-4 (Fig. 6)
    +-- S04_fig07_algorithm_comparison_case4.pdf
    |     Algorithm comparison, Case 4 (Fig. 7)
    +-- S04_fig08_tac_heatmap.pdf
    |     TAC heatmap, all algorithms and cases (Fig. 8)
    +-- S04_fig09_charged_generalisation.pdf
    |     CHARGED city generalisation (Fig. 9)
    +-- S06_fig01_auc_comparison.pdf
    |     AUC comparison and mean rank (Fig. 10)
    +-- S06_fig02_convergence_speed.pdf
    |     Convergence speed heatmap (Fig. 11)
    +-- S06_fig03_speed_vs_quality.pdf
    |     Algorithm speed vs AUC quality scatter
    +-- S06_fig04_convergence_auc_case4.pdf
    |     Case 4 convergence curves with AUC shading
    +-- S07_fig01_tornado_chart.pdf
    |     One-way sensitivity tornado chart (all parameters)
    +-- S07_fig02_alpha_sensitivity.pdf
    |     TAC and SoH vs alpha_comm (Fig. 12)
    +-- S07_fig03_kp_sensitivity.pdf
    |     TAC and grid cost vs kp (Fig. 13)
    +-- S08_fig01_boxplot_friedman.pdf
    |     30-run TAC box plot and Friedman rank chart (Fig. 14)
    +-- S08_fig02_mean_std.pdf
          Mean +/- SD TAC with best-result markers
```

---

## Key Results (Table IV)

| Case | Algorithm | TAC ($/yr) | PV (kWp) | BESS (kWh) | SC (mod) |
|------|-----------|-----------|----------|------------|---------|
| Case 1 (PV+Grid) | All | 25,621 | 47.1 | -- | -- |
| Case 2 (PV+BESS+Grid) | **GWO** | **22,786** | 53.9 | 94.9 | -- |
| Case 3 (+Degradation) | **GWO** | **22,786** | 53.8 | 95.3 | -- |
| Case 4 (Proposed) | **GWO** | **20,659** | 61.3 | 137.6 | 17 |

SC integration reduces BESS cycles from 247 to 195/yr (21.1% reduction)
and total TAC by 9.3% relative to Case 3.

---

## Statistical Validation (Table IX, S08)

30 independent runs per algorithm, Case 4 only,
N_iter=100, N_pop=15, seeds 1000-1029.

| Algorithm | Mean TAC ($/yr) | SD ($/yr) | CV (%) | Friedman rank |
|-----------|----------------|-----------|--------|---------------|
| **GWO** | **20,683** | **10.97** | **0.053** | **1.00** |
| ARO | 20,817 | 66.68 | 0.320 | 2.03 |
| BBO | 21,364 | 312.48 | 1.463 | 3.47 |
| AO | 21,387 | 334.01 | 1.562 | 3.50 |

Friedman: chi2=79.24, p<0.0001.
Wilcoxon (GWO vs others): all p<0.0001.
**GWO is the recommended solver** (CV=0.053%, near-deterministic).

---

## Datasets (External Links)

Raw datasets are NOT included in this repository due to their size
and individual licensing terms. They are publicly available at:

| Dataset | Source | Access |
|---------|--------|--------|
| NASA PCoE Battery Aging (B0005-B0018) | [NASA PCoE Repository](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/) | Free, public |
| ACN-Data EV Charging Sessions (JPL Arroyo Garage) | [ACN-Data Portal](https://ev.caltech.edu/dataset) | Free, registration |
| PVGIS-ERA5 Irradiance (JPL Pasadena 2020) | [PVGIS Tool](https://re.jrc.ec.europa.eu/pvg_tools/en/) | Free, public |
| CHARGED City Demand Profiles | [Guo et al. 2025, Scientific Data](https://doi.org/10.1038/s41597-025-05584-7) | Free, public |

---

## How to Reproduce Results

Simulation pipeline scripts are available from the corresponding author
upon reasonable request. The following sequence was used:

```
S01 --> S02 --> S03 --> S04 --> S05 --> S06 --> S07 --> S08
```

| Script | Purpose | Runtime |
|--------|---------|---------|
| S01 | EV load profile from ACN-Data + NASA degradation model | ~5 min |
| S02 | PV generation profile from PVGIS-ERA5 | ~2 min |
| S03 | Main optimisation (GWO/BBO/AO/ARO, 4 cases, pop=50, iter=500) | ~156 min |
| S04 | All publication figures | ~10 min |
| S05 | CHARGED city generalisation | ~20 min |
| S06 | AUC and convergence speed analysis | <1 min |
| S07 | Sensitivity analysis (alpha_comm, kp, economic) | ~5 min |
| S08 | 30-run statistical validation (Case 4) | ~280 min |

**Hardware used:** HP Victus (AMD Ryzen 9 8945HS, 16 GB RAM, Manjaro Linux)

**Software:** Python 3.13, NumPy, SciPy, Pandas, Matplotlib

---

## Verification

Every number in every table can be verified directly from the CSV files
in this repository:

| Paper table | Verification file |
|-------------|------------------|
| Table IV (Optimal sizing) | `OUTPUT/S03/S03_R01_main_results_table_full.csv` |
| Table V (CHARGED cities) | `OUTPUT/S05/S05_R01_charged_city_results.csv` |
| Table VI (Algorithm performance) | `OUTPUT/S06/S06_R01_auc_analysis.csv` |
| Table VII (alpha sensitivity) | `OUTPUT/S07/S07_R01_alpha_sensitivity.csv` |
| Table VIII (kp sensitivity) | `OUTPUT/S07/S07_R02_kp_sensitivity.csv` |
| Table IX (30-run statistics) | `OUTPUT/S08/S08_R01_summary_statistics.csv` |
| Wilcoxon p-values | `OUTPUT/S08/S08_R02_wilcoxon_results.csv` |
| Friedman test | `OUTPUT/S08/S08_R04_friedman_summary.csv` |
| Raw 30-run TAC values | `OUTPUT/S08/S08_progress.json` |

---

## Citation

If you use these results in your research, please cite:

```bibtex
@article{majumdar2026ev,
  author  = {Majumdar, Kingsuk and Ghosh, Sohini and
             Kumar, Nishant and Ghosh, Indrani},
  title   = {Degradation-Aware Optimal Sizing Framework for
             Grid-Interactive {EV} Charging Stations with {PV},
             {BESS}, and Supercapacitor: Real Dataset Validation
             Using {NASA} {PCoE}, {ACN-Data}, and {CHARGED}},
  journal = {Modern Power Systems and Clean Energy},
  year    = {2026},
  note    = {Under review},
  doi     = {10.5281/zenodo.XXXXXXX}
}
```

---

## Authors and Contact

| Author | Affiliation | ORCID | Email |
|--------|------------|-------|-------|
| **Kingsuk Majumdar** (Corresponding) | Dept. of Electrical Engineering, Dr. B. C. Roy Engineering College, Durgapur 713206, India | [0000-0001-7224-4862](https://orcid.org/0000-0001-7224-4862) | kingsuk.majumdar@bcrec.ac.in |
| Sohini Ghosh | Dept. of Economics (BSH), Dr. B. C. Roy Engineering College, Durgapur 713206, India | [0009-0008-8266-7701](https://orcid.org/0009-0008-8266-7701) | sohini.ghosh@bcrec.ac.in |
| Nishant Kumar | Dept. of Electrical Engineering, IIT Jodhpur, Rajasthan 342030, India | [0009-0000-1235-4330](https://orcid.org/0009-0000-1235-4330) | nishantkumar@iitj.ac.in |
| Indrani Ghosh | Dept. of Electrical Engineering, Dr. B. C. Roy Engineering College, Durgapur 713206, India | [0009-0004-0429-7443](https://orcid.org/0009-0004-0429-7443) | xxxxxx@gmail.com |

---

## License

Results data and figures: [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

You are free to share and adapt this material for any purpose,
provided appropriate credit is given.

---

## Repository Version

**v1.0** -- August 2026 (MPCE submission)

Zenodo DOI: [10.5281/zenodo.XXXXXXX](https://doi.org/10.5281/zenodo.XXXXXXX)

GitHub: [https://github.com/KingsukMajumdar/2026-07-11_J07__NASA_EV_SC](https://github.com/KingsukMajumdar/2026-07-11_J07__NASA_EV_SC)
