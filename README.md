# Staphylococcus pseudintermedius Genomics – Uruguay (2026)

This repository contains the full genomic analysis of 10 canine *Staphylococcus pseudintermedius* isolates from Uruguay, including genome assembly, annotation, phylogenetics, and antimicrobial resistance characterization.

---

## Overview

Whole-genome sequencing (WGS) was performed using Illumina technology. The analysis workflow includes:

- Genome assembly
- Genome annotation
- Phylogenetic analysis (Coregenome identification was done with panaroo)
- SNP extraction
- Antimicrobial resistance (AMR) profiling with Resfinder
- SCCmec typing
- Multi-locus sequence typing (MLST)

A large-scale comparative analysis was performed including >3,500 publicly available genomes from NCBI.

---

## Workflow Summary

### 1. Genome Assembly and Annotation
- Assemblies generated using **Unicycler**
- Genome annotation performed using **Prokka**

---

### 2. Phylogenetic Analysis
- Pangenome construction using **Panaroo** (not included in this repository due to size limitations; available upon request)
- Core gene alignment generated (not included in this repository due to size limitations; available upon request)
- SNP extraction using **SNP-sites**
- Phylogenetic tree inferred with **FastTree**

---

### 3. Antimicrobial Resistance Analysis
- Acquired resistance genes identified using **ResFinder**
- Point mutations analyzed with **PointFinder**

---

### 4. SCCmec Typing
- SCCmec elements identified using **SCCmecFinder**

---

### 5. MLST Typing
- Sequence types assigned using the **MLST** tool

---

## Repository Structure

- `Phylogenetic_Analyses/` → Panaroo, SNP-sites, FastTree pipeline  
- `ARGenes/` → ResFinder and PointFinder analysis  
- `MLST/` → MLST typing results  
- `Assembly/` → Genome assemblies (.fna)  
- `Prokka_Annotation_UruguayanGenomes/` → Prokka output files (.gff, etc.)  

---

## Sample Codes and Strains (Uruguay)

| Code | Strain |
|------|--------|
| xxa  | E13    |
| xxb  | E8     |
| xxc  | M12    |
| xxd  | M1     |
| xxe  | RAM22  |
| xxf  | RAM23  |
| xxg  | RAM33  |
| xxh  | RAM46  |
| xxi  | RAM54  |
| xxj  | RAM87  |

---

## Data

- Assemblies and annotations generated in this study

---

## Reproducibility

Each analysis step is documented in its corresponding README:

- Phylogenetic pipeline
- ResFinder / SCCmec pipeline
- MLST pipeline

All tools were installed via Conda environments.  
Users are encouraged to check software versions in the MS.

---

## Notes

- Custom scripts (e.g., `Nomine.scp`, `MLST_list_fna.scp`) are included for batch processing and result formatting.
- Some intermediate files may be large and are available upon request.

---

## Contact

For data access or collaboration:

**airiarte@higiene.edu.uy**
