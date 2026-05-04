# 🧬 Basic Nanopore Data Processing

## 📂 Merge FASTQ files

```bash
cat *fastq.gz > allfiles.fastq.gz
```

## 🧬 Alignment - [Minimap2](https://github.com/lh3/minimap2)

```bash
minimap2 --MD -a "$ref_hg38" allfiles.fastq.gz > mapped.sam
```

## 🔄 Convert SAM to BAM

```bash
samtools view -bS mapped.sam > mapped.bam
```

## 📊 Sorting

```bash
samtools sort mapped.bam -o mapped.sorted.bam
```

## 📌 Indexing

```bash
samtools index mapped.sorted.bam
```

## 🧬 Structural Variant Calling - [Sniffles](https://github.com/fritzsedlazeck/sniffles)

```bash
sniffles -i mapped.sorted.bam -v variants.vcf
sniffles -i mapped.sorted.bam --reference "$ref_hg38" --non-germline -v variants_nongerm.vcf
```

## 🧬 Annotation (AnnotSV)

```bash
AnnotSV -SVinputFile variants.vcf
```

## 🧬 SNV calling - [longshot](https://github.com/pjedge/longshot)

```
longshot --bam <bam_file> --ref <ref_path> --out <output_file>
```

## Other pipelines and tools

- [wf-human-variation-Nextflow pipeline](https://github.com/epi2me-labs/wf-human-variation)
- [Clair3](https://github.com/HKU-BAL/Clair3)
- [NanoCaller](https://github.com/WGLab/NanoCaller)
