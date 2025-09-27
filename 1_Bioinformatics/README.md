This folder contains the scripts for each step of my bioinformatics pipeline to process raw 3' RNA sequences to a counts matrix (aligned to the *Pocillopora damicornis* genome from Cunning et al. 2016).

Pipeline:

**Combining reads –> FastQC –> Trimmomatic –> FastQC –> STAR –> FeatureCounts**

Forward reads on lanes 1 and 2 were concatenated. Next, the quality of the raw forward reads and reverse reads were assessed using FASTQC (Brown et al. 2017). Adapters were trimmed using the Trimmomatic v0.36 (Bolger et al. 2014). Using STAR v2.5.3a and two-pass mode (Dobin et al. 2013), forward and reverse reads were aligned to the P. damicornis genome (Cunning et al. 2018). Aligned reads were quantified using featureCounts in Subread v1.6.0 (Liao et al. 2014) and then the counts matrix was imported into R (v4.2.1) and RStudio (v2022.12.0+353).
