# Engelhardia-genome-pipeline

This repository contains the command-line workflow used for the genome survey of five *Engelhardia* species. The analysis includes K-mer-based estimation of genome size, heterozygosity, and repeat content using Jellyfish and GenomeScope2.

## 🧬 Species Analyzed

- E. spicata var. spicata
- E. spicata var. colebrookeana
- E. spicata var. aceriflora
- E. roxburghiana
  E. fenzelii

## 📘 Methods Summary

- K-mer frequency histograms were generated using Jellyfish v2.3.0 across a range of K values (19–43).
- GenomeScope2 was used to estimate genome size, heterozygosity, and repeat content from the K-mer histograms.
- The quality of the histograms was evaluated based on peak clarity, error separation, and background noise.
- Model fitting quality was assessed using the model fit R² and residual error.

## 💻 Example Commands

bash
# Count K-mers (K=43)
jellyfish count  -m 43 -s 20G -t 30 -o 43mer_out  -C  <(zcat Read_1.fq.gz) <(zcat Read_2.fq.gz)

# Generate histogram
jellyfish histo -o 43mer_out.histo 43mer_out

# Run GenomeScope2
Rscript genomescope/genomescope.R  43mer_out.histo 43 150 kmer_43
