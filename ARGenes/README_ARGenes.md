# Antimicrobial Resistance & SCCmec Analysis Pipeline

This document describes the workflow for detecting antimicrobial resistance genes using ResFinder and SCCmec typing.

---

## ResFinder

### Installation (Conda)

conda create -n resfinder_env -c bioconda resfinder
conda activate resfinder_env

---

### Databases

# Acquired resistance genes database
git clone https://bitbucket.org/genomicepidemiology/resfinder_db.git

# Point mutation database (PointFinder)
git clone https://bitbucket.org/genomicepidemiology/pointfinder_db.git

---

### Database Setup

# Install ResFinder database
cd resfinder_db

python3 INSTALL.py

cd ..

# Install PointFinder database
cd pointfinder_db
python3 INSTALL.py
cd ..

---

### Run ResFinder (multiple genomes in parallel)

parallel -j 10 'python3 -m resfinder -ifa {} -o {.}_resfinder.out --db_path_res /home/andres/PROGRAMAS/resfinder/resfinder_db --acquired' ::: *.fna

---

## SCCmec Finder

### Installation (Conda)

conda create -n sccmec_env -c conda-forge -c bioconda sccmec
conda activate sccmec_env

---

### Run SCCmec (multiple genomes in parallel)

parallel -j 10 'sccmec -i {} -o {/.}' ::: ../Assemblies/*.fna

---

## Requirements

- Conda (Miniconda or Anaconda)
- ResFinder
- SCCmec
- GNU Parallel
- Python 3

---

## Notes

- Update database paths (--db_res) according to your installation directory.
- Output folders will be created automatically for each genome.
- Adjust the number of parallel jobs (-j) based on available CPU cores.
- Software and database versions are included in the MS.

