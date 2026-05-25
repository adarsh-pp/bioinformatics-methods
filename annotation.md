# 🧬 Variant Annotation Utilities

Common tools and commands for structural and small variant annotation.

---

## 🧬 Structural Variant Annotation (AnnotSV)

```bash
AnnotSV -SVinputFile variants.vcf
```

## 🧬 ANNOVAR Annotation

```bash
table_annovar.pl input.vcf humandb/ \
-buildver hg38 \
-out annotated_output \
-remove \
-protocol refGene,clinvar_20240917,gnomad41_exome \
-operation g,f,f \
-nastring . \
-vcfinput
```

## 🔄 Convert VCF to ANNOVAR Input

```bash
convert2annovar.pl \
-format vcf4 \
-withzyg \
--includeinfo \
input.vcf \
-out output.avinput
```

## 🧬 SnpEff Annotation

```bash
snpEff hg38 input.vcf > annotated.vcf
```
💡 Predicts functional effects of variants.

## 📊 Extract Functional Annotations from VCF

```bash
bcftools query \
-f '%CHROM\t%POS\t%REF\t%ALT\t%INFO\n' \
annotated.vcf
```

## 📌 Common Human Variant Annotation Databases

- RefGene
- ClinVar
- dbnsfp
- gnomAD
- dbSNP
- ExAC
- 1000 Genomes

## 🔬 Additional Annotation Tool
- [VEP](https://www.ensembl.org/info/docs/tools/vep/index.html)
