# ProcessNGS

## Description
Pipeline for processing high-troughput sequencing (NGS) data. This workflow is suited for paired-end reads from whole-exome sequencing (WES) or whole genome sequencing (WGS), and includes the tasks of quality control, mapping reads to reference genome, remove duplicates and base recalibration. 

## Environment
The different tasks were run in a high-performance computing cluster (*Finisterrae II*) managed by Slurm scheduling system.

## Sample data
The sample datasets used to test the pipeline are WES data from a colorectal tumor sample and its normal-paired sample. The output of this workflow was then used for testing the pipeline of somatic variant calling.

## Reference genome
The reference human genome used for mapping reads is hg19 (aka b37).

## Input 
Paired-end sequencing reads (Fastq format).

## Output
Alignment fimes (SAM/BAM). 

## Time and computing costs
Time and cost estimates can vary depending on the performance of computing cluster, the number of samples and their size.

## Main tasks
Quality control of raw files (FastQC)
Trim adaptors (CutAdapt)
Mapping reads to reference (BWA) and sort alignments (Picard SortSam)
Mark PCR-derived duplicates (Picard MarkDuplicates)
Base recalibration (BaseRecalibrator)

## Evaluation tasks
Quality control and alignment stats (flagstats)
Genome Coverage (Bedtools)
Build recalibration model (BaseRecalibrator)
