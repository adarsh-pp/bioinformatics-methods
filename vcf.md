# 🧬 VCF Utilities

Common operations for handling VCF (Variant Call Format) files.

---

## 📄 View VCF Header

```bash
bcftools view -h input.vcf.gz
```

## 🔍 View Variant Records

```bash
bcftools view input.vcf.gz
```

## 🧬 Extract SNPs Only

```bash
bcftools view -v snps input.vcf.gz -o snps.vcf
```

## 🧬 Extract Indels Only

```bash
bcftools view -v indels input.vcf.gz -o indels.vcf
```

## 📌 Filter by Quality

```bash
bcftools filter -i 'QUAL>30' input.vcf.gz -o filtered.vcf
```

## 📏 Filter by Read Depth

```bash
bcftools filter -i 'DP>20' input.vcf.gz -o depth_filtered.vcf
```

## 🧬 Extract Variants from Region

```bash
bcftools view -r chr1:100000-200000 input.vcf.gz -o region.vcf
```

## 📂 Compress VCF

```bash
bgzip input.vcf
```

## 📌 Index VCF

```bash
tabix -p vcf input.vcf.gz
```

💡 Required for rapid querying of compressed VCF files.

## 🔎 Query Specific Fields

```bash
bcftools query -f '%CHROM\t%POS\t%REF\t%ALT\n' input.vcf.gz
```

## 🔄 Convert VCF to Tabular Format

```bash
bcftools query \
-f '%CHROM\t%POS\t%REF\t%ALT\t%QUAL\n' \
input.vcf.gz > variants.tsv
```

## 📊 Count Variants

```bash
bcftools view -H input.vcf.gz | wc -l
```

## 🧬 Normalize Variants

```bash
bcftools norm -f reference.fa input.vcf.gz -o normalized.vcf
```
