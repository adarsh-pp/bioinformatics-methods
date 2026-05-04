# 🧬 FASTQ Utilities

Common operations for handling FASTQ files.

---

## 🔢 Count Reads

```bash
zcat input.fastq.gz | wc -l
```
💡 Divide the output by 4 to get the total number of reads.

## 📂 Merge Multiple FASTQ Files

```bash
cat *.fastq.gz > merged.fastq.gz
```
💡 Useful when sequencing output is split across multiple files.

## 🔍 Extract Reads by ID

```bash
seqtk subseq input.fastq read_ids.txt > output.fastq
```

## 🔄 Convert FASTQ to FASTA

```bash
seqtk seq -a input.fastq > output.fasta
```

## 🧬 Extract Paired-End Reads

```bash
seqtk subseq input_R1.fastq.gz ids.txt > output_R1.fastq
seqtk subseq input_R2.fastq.gz ids.txt > output_R2.fastq
```
💡 Ensure paired reads remain synchronized.

## 🗜️ Compress FASTQ

```bash
gzip input.fastq
```

## 📤 Decompress FASTQ

```bash
gunzip input.fastq.gz
```
