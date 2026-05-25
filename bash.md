# 🧬 Bash Utilities

Common shell commands and scripting utilities used in bioinformatics workflows.

---

## 📂 Loop Through Files

```bash
for file in *.fastq.gz; do
    echo $file
done
```

## 🔄 Rename Files

```bash
for file in *.fastq.gz; do
    mv "$file" "${file/sample_/}"
done
```
💡 Removes sample_ from filenames.

## 🔍 Search for Pattern in Files

```bash
grep "pattern" filename.txt
```

## 🔎 Search Recursively

```bash
grep -r "pattern" directory/
```

## ✂️ Extract Columns with awk

```bash
awk '{print $1,$2,$3}' input.txt
```

## 📊 Count Lines in File

```bash
wc -l input.txt
```

## 🔢 Count FASTQ Reads

```bash
zcat input.fastq.gz | wc -l
```

## 📂 Extract Specific Lines

```bash
sed -n '1,10p' input.txt
```

## 🔄 Replace Text in File

```bash
sed 's/old/new/g' input.txt
```

## 📌 Sort File

```bash
sort input.txt > sorted.txt
```

## 🧬 Remove Duplicate Lines

```bash
sort input.txt | uniq
```

## 📊 Monitor Running Processes

```bash
htop
```

## 💾 Check Disk Usage

```bash
du -sh *
```

## 📁 Check File Size

```bash
ls -lh
```

## 🔍 Find Files

```bash
find . -name "*.bam"
```

## 📂 Extract Compressed Files

```bash
# tar.gz
tar -xvzf archive.tar.gz

# zip
unzip archive.zip
```

## 🗜️ Compress Files

```bash
# gzip
gzip input.fastq

# tar.gz
tar -cvzf archive.tar.gz directory/
```

## 🔬 Run Command in Background

```bash
nohup command > output.log &
```

## 📌 Check Available Memory

```bash
free -h
```

## ⚡ Count Number of Files

```bash
ls | wc -l
```
