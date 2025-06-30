## Input Data Description

- `reads.fq.gz`: Quality-filtered Illumina PE150 reads
- reads (R1, R2) were used for Jellyfish counting
- No adapter trimming was needed

## Output

- `mer_counts.jf`: Jellyfish binary output
- `kmer_histogram.txt`: Histogram used by GenomeScope2
- `output_dir/`: GenomeScope2 results (PNG, TXT, HTML)
