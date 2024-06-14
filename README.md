Analysis process of RNA-seq and acRIP-seq
The integrity of the sequencing data and quality control was performed with FastQC (version 2.11.5).
Sequence trimming was performed with Trimmomatic (version 0.39).
The remaining reads were aligned to the mouse genome Mus musculus GRCm38.95 by STAR (version 2.7.5c).
Uniquely mapped reads were subjected to downstream analysis. Samtools (version 1.9)36 was used for the file format conversion required during the alignment and quantification steps.
Deeptools83 was used to analyze the degree of correlation between different biological replicates in the vehicle group and treatment groups, respectively, and to observe inter-group differences and intra-group similarity. 
Fingerprints provide the relative enrichment of the IP samples with respect to the input.
The ac4C-enriched regions (peaks) in each ac4C-RIP sample were detected by exomePeak (version 2.17.0)
