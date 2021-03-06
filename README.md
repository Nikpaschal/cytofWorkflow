# CyTOF workflow: differential discovery in high-throughput high-dimensional cytometry datasets

## Abstract

High dimensional mass and flow cytometry (HDCyto) experiments have become a
method of choice for high throughput interrogation and characterization of cell
populations. Here, we present an R-based pipeline for differential analyses of
HDCyto data, largely based on Bioconductor packages. We computationally define
cell populations using FlowSOM clustering, and facilitate an optional but
reproducible strategy for manual merging of algorithm-generated clusters. Our
workflow offers different analysis paths, including association of cell type
abundance with a phenotype or changes in signaling markers within specific
subpopulations, or differential analyses of aggregated signals. Importantly,
the differential analyses we show are based on regression frameworks where the
HDCyto data is the response; thus, we are able to model arbitrary experimental
designs, such as those with batch effects, paired designs and so on. In
particular, we apply generalized linear mixed models to analyses of cell
population abundance or cell-population-specific analyses of signaling markers,
allowing overdispersion in cell count or aggregated signals across samples to
be appropriately modeled. To support the formal statistical analyses, we
encourage exploratory data analysis at every step, including quality control
(e.g. multi-dimensional scaling  plots), reporting of clustering results
(dimensionality reduction, heatmaps with dendrograms) and differential analyses
(e.g. plots of aggregated signals).

## Bioconductor installation

The workflow is available on
[Bioconductor](https://www.bioconductor.org/help/workflows/cytofWorkflow/).

All the packages used in this workflow get installed by installing the workflow
corresponding package:

```{r}
source("http://bioconductor.org/workflows.R")
workflowInstall("cytofWorkflow")
```

## GitHub installation

First you need to install `BiocManager`:

```
if (!requireNamespace("BiocManager", quietly=TRUE))
    install.packages("BiocManager")
```

You need to install the `devtools` CRAN package using `BiocManager::install()`
below:

```
BiocManager::install("devtools")
```

Install the workflow from this GitHub repository:

```
BiocManager::install("gosianow/cytofWorkflow", dependencies = TRUE)
```

The workflow can be executed by following the instructions in the
cytofWorkflow.Rmd file available in the
[vignettes directory](https://github.com/gosianow/cytofWorkflow/blob/master/vignettes/cytofWorkflow.Rmd).