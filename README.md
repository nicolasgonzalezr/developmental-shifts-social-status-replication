# Developmental shifts in social status detection

Replication package for **“Developmental Shifts in Social Status Detection Among School-Age Children.”**

**Work in progress:** This project is ongoing. The analyses and replication materials are not yet finalized and may change.

## Replication files

| File | Description |
| --- | --- |
| `Scripts/replicationScript.qmd` | Analysis code, including regression models, bootstrap inference, sensitivity analyses, and table and figure generation. |
| `Data/replicationData.rds` | Study data, including PageRank social status, grade cohort, classroom, body mass index, theory of mind, self-perceived social status, and academic grades. Data will be made available at manuscript submission. |
| `Data/bootMatrixT.rds` | Saved percentile-t bootstrap statistics for the four regression models. |
| `Data/bootMatrixWR.rds` | Saved wild restricted bootstrap statistics for the four regression models. |
| `Data/bootMatrixSV.rds` | Saved bootstrap statistics for the score-variance test of classroom clustering. |
| `Data/bootMatrixWald.rds` | Saved wild restricted bootstrap Wald statistics for the joint test of self-perceived school status and its grade interaction. |
| `Data/bootMatrixWCR.rds` | Saved wild cluster restricted bootstrap statistics used to diagnose the reference distributions for the focal coefficients. |
| `Data/sensitivityTable.rds` | Saved results comparing asymptotic and bootstrap inference under alternative robust variance estimators. |

## Requirements

R and the following packages:

```r
install.packages(c("tidyverse", "readxl", "sandwich", "clubSandwich", "lmtest", "car", "stargazer", "ragg", "kableExtra"))
```

Quarto is needed to render the analysis document.

## Run the analyses

1. Download or clone the repository, preserving the `Data/` and `Scripts/` folders.
2. Set the working directory to `Scripts/` when executing chunks interactively. The data-loading paths are relative to that folder.
3. Apply the adjustments listed below, then open `Scripts/replicationScript.qmd` and execute the R chunks in order.

The script defaults to using saved bootstrap results (`runBootstraps <- FALSE`). Adjust `availableCores` to your computer, or set `parallelSupported <- FALSE` for sequential execution.

To rerun the bootstrap procedures, set `runBootstraps <- TRUE`. The default is 99,999 iterations per procedure, which is computationally intensive. The original parallel configuration used 15 cores; changing the parallel configuration can change the random draws. Use the supplied results to reproduce the reported bootstrap p-values.

With `saveTables <- TRUE`, regression tables are exported as HTML files in the working directory, and the main figure is exported as PNG and TIFF files to `Plots/` at the repository root.

## Contact

Nicolás González-Raposo — nicgonzalezr@udd.cl
