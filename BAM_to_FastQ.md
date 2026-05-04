# 🔄 BAM to FASTQ Conversion

## 🚀 Using [bazam](https://github.com/ssadedin/bazam) + [BBMap Suite](https://jgi.doe.gov/data-and-tools/software-tools/bbtools/bb-tools-user-guide/bbmap-guide/)

```bash
# Converting bam to an interleaved FASTQ format using Bazam
java -jar bazam.jar -bam input.bam > output.fastq

# An interleaved FASTQ file is a type of FASTQ file that contains both the forward and reverse reads of a paired-end fragment in a single file.

# Spliting the single FastQ file into Read1 and Read2
bash /bbmap/reformat.sh in=original.fq out1=R1.fq out2=R2.fq
```

## 🧰 Using [Samtools](https://www.htslib.org/) + [Bedtools](https://bedtools.readthedocs.io/en/latest/)

```bash
# Sort BAM by read name
samtools sort -n input.bam -o input_sorted.bam   # sort reads by identifier-name (-n)

# Convert to FASTQ
bedtools bamtofastq -i input_sorted.bam -fq output_r1.fastq -fq2 output_r2.fastq
```
