This folder contains the scripts for each step of my bioinformatics pipeline:

**FastQC –> Trimmomatic –> FastQC –> STAR –> FeatureCounts**

Methods:

1) RNA Extraction

Total RNA was extracted using the Qiagen RNeasy Minikit. To determine RNA quantity in each extracted sample, a Qubit fluorometer (Version 3.0) was used with the High Sensitivity RNA kit. Total RNA was converted into 3’ complementary DNA (cDNA) using the Lexogen Quantseq FWD Library Preparation kit. Library quality control was performed using the Agilent D1000ScreenTape analysis. 28 samples passed quality control and were sequenced via multiplexing in two lanes for 100 base pair paired-end sequencing using the NOVAseq at the University of Miami, Miller School of Medicine, John P. Hussman Institute for Human Genomics. Each sample was run in both lanes, resulting in two forward and two reverse reads for each sample.

2) Sequence Analysis

Some sequences did not pass initial quality control and were thus removed from downstream analyses. These included all samples from hour 3, and two control samples from hour 5. Therefore, subsequent analysis only includes three biological replicates for the wounded and control treatments at hours 0, 1, 2, and 4 (N=24). Read depth for the selected samples ranged from 15-27 million total reads. Raw mRNA sequence reads will be uploaded to the NCBI Sequence Read Archive (SRA).

3) Bioinformatics

Forward reads on lanes 1 and 2 were concatenated. Next, the quality of the raw forward reads and reverse reads were assessed using FASTQC (Brown et al. 2017). Adapters were trimmed using the Trimmomatic v0.36 (Bolger et al. 2014). Using STAR v2.5.3a and two-pass mode (Dobin et al. 2013), forward and reverse reads were aligned to the P. damicornis genome (Cunning et al. 2018). Aligned reads were quantified using featureCounts in Subread v1.6.0 (Liao et al. 2014) and then the counts matrix was imported into R (v4.2.1) and RStudio (v2022.12.0+353).
