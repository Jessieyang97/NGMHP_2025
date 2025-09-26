# NGMHP_2025
Scripts for reproducing the nonlinear gut microbiota health predictor (NGMHP).
# Description
NGMHP (Nonlinear Gut Microbiota Health Predictor) is a index developed to assess gut health by leveraging nonlinear dimensionality reduction and large-scale integration of human stool metagenomes. Built on 8,677 publicly available samples across diverse studies, NGMHP extends beyond conventional linear indices by capturing complex microbial interactions and latent structures that distinguish healthy from diseased states. By applying kernel principal component analysis (KPCA) and subsequent CPCA, NGMHP identifies four latent health patterns, thereby reflecting the ecological heterogeneity of the human gut microbiome. Additionally, NGMHP incorporates SPE decomposition to quantify the individual contribution of microbial taxa to overall health status, enabling personalized risk interpretation and dietary recommendations. Lower NGMHP scores indicate microbiome profiles aligned with health-promoting features, whereas higher scores reflect perturbations associated with disease.
# Basic Usage of NGMHP
Step 1. Quality control and preprocessing
Perform standard quality control (QC) on raw metagenomic sequencing data (fastq files), including trimming and filtering of low-quality reads.
Step 2. Taxonomic profiling
Run MetaPhlAn2 at the species level to obtain species-level relative abundance profiles.
Step 3. Table merging
If analyzing multiple samples, merge individual MetaPhlAn2 outputs using merge_metaphlan_tables.py (provided within the MetaPhlAn2 pipeline). Save the merged abundance table as .csv, with species names in the first column and relative abundances in subsequent columns.
Step 4. NGMHP computation
Load the merged species-abundance table into the NGMHP Matlab scripts to compute:
Global health index (NGMHP score)
Latent health patterns (hidden layer representation)
Species-level contribution maps (personalized deviation profiles)
Step 5. Downstream analysis and visualization
Export the outputs and use the Python scripts provided for further statistical analysis, plotting of health distributions, trajectory tracking in longitudinal cohorts, and visualization of personalized contribution profiles.

The source code and detailed documentation will be made publicly available upon acceptance of the manuscript.
