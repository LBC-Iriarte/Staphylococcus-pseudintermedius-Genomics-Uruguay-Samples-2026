# MLST Analysis

This workflow describes how to perform Multi-Locus Sequence Typing (MLST) on genome assemblies using the mlst tool.

---

## Installation

Install via Conda:

conda install -c bioconda mlst

Tool repository: https://github.com/tseemann/mlst  
Author: Torsten Seemann

---

## Input

- Genome assemblies in .fna format (e.g., Uruguayan S. pseudintermedius genomes generated in this work and for all genomes downloaded from NCBI)

---

## Run MLST

Run MLST on all assemblies using a custom script:

./MLST_list_fna.scp Path_where_all_fna_files_are Mlst.output.tsv

---

## Output

- Mlst.output.tsv: Tab-delimited file containing MLST results for all genomes

---

## Notes

- MLST_list_fna.scp is a custom script used to batch-process multiple .fna files.
- Ensure all input files are in the specified directory.
