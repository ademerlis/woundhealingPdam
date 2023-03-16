#!/bin/bash
#BSUB -J featurecounts_WH
#BSUB -q general
#BSUB -P transcriptomics
#BSUB -o /projects/scratch/transcriptomics/allysondemerlis/scripts/featurecounts_WH.out
#BSUB -e /projects/scratch/transcriptomics/allysondemerlis/scripts/featurecounts_WH.err
#BSUB -n 8

#/projects/scratch/transcriptomics/allysondemerlis/scripts/featurecounts_WH.job
#purpose: quantify Pocillopora damicornis aligned RNAseq transcript abundances using 
#featureCounts program to create a counts table on Pegasus
#Thanks Mike!

#specify variable containing sequence file prefixes, experiment design and directory paths

and="/projects/scratch/transcriptomics/allysondemerlis"

${and}/programs/subread-1.6.0-Linux-x86_64/bin/featureCounts -t gene \
-g ID \
-a ${and}/sequences/Pdam_genome/pdam_genome.gff \
-o ${and}/projects/wound_healing/STARcounts/WH_Pdam.counts \
${and}/projects/wound_healing/STARalign_results/*Aligned.out.bam

