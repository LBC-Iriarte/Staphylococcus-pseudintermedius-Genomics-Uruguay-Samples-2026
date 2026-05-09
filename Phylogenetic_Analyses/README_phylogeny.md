# Phylogenetic Pipeline

This repository contains a pipeline for building a phylogenetic tree from annotated bacterial genomes using core gene alignments and SNP extraction.

---

## Input Files

- `CODES_ASSEMBLYACC.tab`  
  Tab-delimited file mapping sample codes to assembly accession numbers.

- `*.gff`  
  Genome annotation files generated with Prokka

---

## Pipeline Steps

1. Prepare GFF file list
   ls *.gff > gff.lista
   

3. Pangenome analysis (Panaroo)
   panaroo -i gff.lista -o results --clean-mode strict -a core --aligner mafft --core_threshold 0.95 -t 30

   Output:
   - core_gene_alignment.aln

4. SNP extraction (SNP-sites)
   snp-sites -o core_gene_alignment.SNPs.fas core_gene_alignment.aln

5. Phylogenetic tree construction (FastTree)
   FastTreeMP -gtr -nt core_gene_alignment.SNPs.fas > core_gene_alignment.SNPs.fas.FT.nwk

6. Rename tree labels
   ./Nomine.scp core_gene_alignment.SNPs.fas.FT.nwk CODES_ASSEMBLYACC.tab

   Output:
   - core_gene_alignment.SNPs.fas.FT.nwk.LN.tre

   This is the final tree used for downstream analyses.

---

## Requirements

Make sure the following tools are installed and available in your PATH:

- Prokka  
- Panaroo  
- SNP-sites  
- FastTree  

---

## Notes

- Nomine.scp is a custom script used to replace tip labels in the Newick tree using the mapping file.
- All intermediate and output files may be available upon request (please write to airiarte@higiene.edu.uy)

---

## Contact
For questions:
airiarte@higiene.edu.uy
