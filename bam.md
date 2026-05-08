# 🧬 BAM Utilities

Common operations for handling BAM alignment files.

---

## 🔄 Convert SAM to BAM

```bash
samtools view -bS input.sam > output.bam
```
💡 Converts SAM alignment file into BAM format.

## 📊 Sort BAM File

```bash
samtools sort input.bam -o sorted.bam
```
💡 Required before indexing and many downstream analyses.

## 📌 Index BAM File

```bash
samtools index sorted.bam
```
💡 Generates .bai index for rapid access.

## 📈 Alignment Statistics

```bash
samtools flagstat input.bam
```
💡 Provides summary statistics for mapped and unmapped reads.

## 🔍 View BAM Header

```bash
samtools view -H input.bam
```

## 🧬 Extract Reads from Region

```bash
samtools view -b input.bam chr1:100000-200000 > region.bam
```
💡 Extracts alignments from a specific genomic region.

## 📏 Calculate Depth

```bash
samtools depth input.bam > depth.txt
```

## 🔀 Sort BAM by Read Name

```bash
samtools sort -n input.bam -o sorted_by_name.bam
```

## 🔄 Convert BAM to FASTQ

Using SAMtools

```bash
samtools fastq input.bam > output.fastq
```

Using Bedtools

```bash
bedtools bamtofastq \
-i sorted_by_name.bam \
-fq output_R1.fastq \
-fq2 output_R2.fastq
```

Using Bazam and BBMap Suite

```bash
# Converting bam to an interleaved FASTQ format using Bazam
java -jar bazam.jar -bam input.bam > output.fastq

# An interleaved FASTQ file is a type of FASTQ file that contains both the forward and reverse reads of a paired-end fragment in a single file.

# Spliting the single FastQ file into Read1 and Read2
bash /bbmap/reformat.sh in=original.fq out1=R1.fq out2=R2.fq
```

## 🗑️ Remove Duplicates

```bash
samtools markdup -r input.bam deduplicated.bam
```

## 📂 Merge BAM Files

```bash
samtools merge merged.bam sample1.bam sample2.bam
```
