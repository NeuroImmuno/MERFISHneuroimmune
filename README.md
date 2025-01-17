# MERFISHneuroimmune
The Maternal Gut-Immune Axis Programs the Neuroimmune Landscape of the Developing Brain
This GitHub repository documents the core analyses of the study Neuroimmune landscape, which includes MERFISH analysis for developing mouse brain during mid and late gestation(n=3), alterations after maternal immune activation and microbiome depletion during pregnancy and snATACseq data analysis in embryonic brain at E12.5 (males and females).

**Data availability**
The raw datasets as well as cell ranger processed data analyzed in this study are available in the Gene Expression Omnibus repository under accession numbers: GSE269617 and GSE276002

**Sofware enviornment**
The analyses were performed within an R 4.2 enviornment.

R version 4.2.1 (2022-06-23) Platform: x86_64-pc-linux-gnu (64-bit) Running under: AlmaLinux 8.8 (Sapphire Caracal)

The following packages and versions are required and should be loaded prior to running the analysis

Seurat_5.0.1
dplyr_1.1.4
ggrepel_0.9.6
circlize_0.4.15
ComplexHeatmap_2.12.1
future.apply_1.11.2
FNN_1.1.4.1
patchwork_1.3.0
CellChat_1.6.1
igraph_2.0.3
future_1.34.0
reshape2_1.4.4
lubridate_1.9.2
forcats_1.0.0
stringr_1.5.1
purrr_1.0.2
readr_2.1.5
tidyr_1.3.1
tibble_3.2.1
ggplot2_3.5.1
tidyverse_2.0.0
nlme_3.1-157
reticulate_1.39.0
pbapply_1.7-2
sf_1.0-15
SeuratObject_5.0.1
sp_2.1-4
MAST_1.24.1
SingleCellExperiment_1.18.1
SummarizedExperiment_1.26.1
Biobase_2.56.0
GenomicRanges_1.48.0
GenomeInfoDb_1.34.9
IRanges_2.30.0
S4Vectors_0.34.0
BiocGenerics_0.42.0
MatrixGenerics_1.8.1
matrixStats_1.1.0
lme4_1.1-10
gridExtra_2.3


PYTHON 3 Packages
numpy
pandas 
scanpy
sys
scrublet
matplotlib
observable_jupyter
clustergrammer2
scipy.stats.stats 
copy
glob
anndata
scipy.spatial
tqdm

**Notes: **-In instances where the same bioinformatic analysis was applied several times (i.e. multiple samples), one example script is provided

- The snATAC-seq scripts are processed as it is for all samples ( specific script). Input data is the cellranger processed files avaiable in GEO accession number:GSE276002
- MERFISH Scripts, the order of operations was as follows:

0. Merfish QC filteration -  (general script) - Input data is metadata and cell by gene file for each sample available in GEO accession number: GSE269617

1. Create seurat object for each sample and integrate all samples (general script provided to create seurat object for each sample and their integration)

2. Perform differential analysis for each celltypes to compare E14 and E18 (specific scripts for E14 and E18 comparison)

3. Perform micro environmnet analsis comparing E14 and E18 samples (Specific script)- Indput data is merged seurat object for E14 and E18 dataset.

4. Create micro environment spatial plots (general script - uses two datasets to generate spatial plots.
  
5. Impute scRNAseq data from previous study to MERFISH data - the input scRNAseq data is avaiable at GEO accession number: GSE148237 

6. Create seurat object for each sample and integrate all samples (MIA-males, MIA-females, PBS-males, PBS-females (n=3)) - general script provided to create seurat object for each sample and their integration

7. Differential analysis and volcano plot code to compare 4 conditions - general script shows example to compare MIA males with PBS males.

8. Create seurat object for each sample and integrate all samples (MMD-males, MMD-females) - general script provided to create seurat object for each sample and their integration with PBS samples

9. Differential analysis and volcano plot code to compare conditions - Specific script shows example to compare MMD with PBS.

10. Perform Ligand-Receptor analysis using cellchat - general script.

11. Python helper script to run cell distance analysis to compare MIA vs PBS/MMD vs PBS.

12. Perform cell distance analysis using above python helper code.
  
