# MERFISHneuroimmune
The Maternal Gut-Immune Axis Programs the Neuroimmune Landscape of the Developing Brain
This GitHub repository documents the core analyses of the Neuroimmune landscape study, which includes 
1. MERFISH analysis for :
	a. Developing mouse brain during mid (E14, n=3) and late gestation (E18, n=3), 
	b. Neuroimmune alterations in embryonic brain after maternal immune activation (compring males and females with respective PBS controls (n=3)) at E14
	c. Neuroimmune alterations in embryonic brian after microbiome depletion during pregnancy at E14 (n=6)
2. Single nuclei ATACseq data analysis in embryonic brain at E12.5 (males and females, n=3).

**Data availability**
1. Single nuclei ATACseq- The raw datasets as well as cell ranger processed data files analyzed in this study are available in the Gene Expression Omnibus repository under accession numbers: GSE276002
2. MerFISH - The processed files in the form of cell by gene and cell metadata files for each sample are available in the Gene Expression Omnibus repository under accession numbers: GSE269617

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

**Code usage**
In instances where the same bioinformatic analysis was applied several times (i.e. multiple samples), one example script is provided

- The snATAC-seq scripts are processed as it is for all samples (specific script). Input data is the cellranger processed files avaiable in GEO accession number: GSE276002
- MERFISH Scripts, the order of operations was as follows:

00. Merfish QC filteration -(general script)- Input data is metadata and cell by gene file for each sample available in GEO accession number: GSE269617

01. Create seurat object for each sample and integrate all samples (general script provided to create seurat object for each sample and their integration)- Input is filtered cell metadata and cell by gene files.

02. Perform differential analysis for each celltypes to compare E14 and E18 (specific scripts for E14 and E18 comparison)

03. Perform micro environmnet analsis comparing E14 and E18 samples (Specific script)- Indput data is merged seurat object for E14 and E18 dataset.

04. Create micro environment spatial plots (general script - uses two datasets to generate spatial plots.
  
05. Impute scRNAseq data from previous study to MERFISH data - the input scRNAseq data is avaiable at GEO accession number: GSE148237 

06. Create seurat object for each sample and integrate all samples (MIA-males, MIA-females, PBS-males, PBS-females (n=3))- general script provided to create seurat object for each sample and their integration

07. Differential analysis and volcano plot code to compare 4 conditions - general script shows example to compare MIA males with PBS males.

08. Create seurat object for each sample and integrate all samples (MMD-males, MMD-females) - general script provided to create seurat object for each sample and their integration with PBS samples

09. Differential analysis and volcano plot code to compare conditions - Specific script shows example to compare MMD with PBS.

10. Perform Ligand-Receptor analysis using cellchat - general script.

11. Python helper script to run cell distance analysis to compare MIA vs PBS/MMD vs PBS.

12. Perform cell distance analysis using above python helper code.
  
