# 🧬 Nanopore Data Processing

Common commands for basic Nanopore sequencing analysis.

---

## 📂 Merge FASTQ Files

```bash
cat *.fastq.gz > all_reads.fastq.gz
```
💡 Useful when sequencing output is split across multiple files.

## 🧬 Alignment with Minimap2

```bash
minimap2 -a --MD reference.fa all_reads.fastq.gz > mapped.sam
```
💡 Align long Nanopore reads to the reference genome.

## 🔄 Convert SAM to BAM

```bash
samtools view -bS mapped.sam > mapped.bam
```

## 📊 Sort BAM File

```bash
samtools sort mapped.bam -o mapped.sorted.bam
```

## 📌 Index BAM File

```bash
samtools index mapped.sorted.bam
```

## 🧬 Structural Variant Calling (Sniffles)

```bash
sniffles -i mapped.sorted.bam -v variants.vcf
```

## 🧬 Non-Germline Structural Variant Calling

```bash
sniffles \
-i mapped.sorted.bam \
--reference reference.fa \
--non-germline \
-v variants_nongermline.vcf
```

## 🧬 Structural Variant Annotation (AnnotSV)

```bash
AnnotSV -SVinputFile variants.vcf
```

## 🔬 SNV Calling with Longshot

```bash
longshot \
--bam mapped.sorted.bam \
--ref reference.fa \
--out variants.vcf
```

---

## 🧬 Additional Nanopore Variant Calling Tools
- [Clair3](https://github.com/HKU-BAL/Clair3)
- [NanoCaller](https://github.com/WGLab/NanoCaller)
- [wf-human-variation](https://github.com/epi2me-labs/wf-human-variation)
