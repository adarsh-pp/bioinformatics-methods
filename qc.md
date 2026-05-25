# 🧬 Quality Control Utilities

Common tools and commands for sequencing quality assessment.

---

## 📊 Run FastQC

```bash
# Single file
fastqc input.fastq.gz

# Multiple files
fastqc *.fastq.gz

# Specify Output Directory
fastqc *.fastq.gz -o fastqc_results/
```
💡 Generates sequencing quality reports for FASTQ files.


## 📊 Aggregate Reports with MultiQC

```bash
# Inside the fastqc folder
multiqc .
```
💡 Combines multiple QC reports into a single summary report.

## ✂️ Adapter Trimming with Trim Galore

```bash
trim_galore input.fastq.gz
```

## ✂️ Paired-End Trimming

```bash
trim_galore --paired sample_R1.fastq.gz sample_R2.fastq.gz
```

## 🔍 Basic Read Statistics

```bash
seqkit stats *.fastq.gz
```

## 📏 Alignment Statistics

```bash
samtools flagstat input.bam
```

## 📈 Coverage Statistics

```bash
samtools depth input.bam > depth.txt
```

## 🧬 Generate Coverage Summary

```bash
mosdepth sample input.bam
```

## 🔬 Read Length Distribution

```bash
seqkit fx2tab --length --name input.fastq.gz
```

## 📌 Check Disk Usage of Sequencing Files

```bash
du -sh *.fastq.gz *.bam *.vcf.gz
```
