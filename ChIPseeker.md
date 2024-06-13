if (!requireNamespace("BiocManager", quietly = TRUE))
install.packages("BiocManager") BiocManager::install("ChIPseeker")
BiocManager::install("fgsea") BiocManager::install("BayesPeak")
BiocManager::install("TxDb.Mmusculus.UCSC.mm10.knownGene")
#查看peak在全基因组的位置 library(ChIPseeker) library(ggplot2)

con_sig_diff_peak \<- readPeakFile\
peak \<-
readPeakFile("F:/ac4C_data/exomePeak/2021_11_17_exomePeak_output/con_sig_diff_peak.bed")
covplot(con_sig_diff_peak)\
======================================= #ChIP peaks结合TSS 区域的情况

library("ChIPseeker") library("ggplot2") library("org.Mm.eg.db")
library("TxDb.Mmusculus.UCSC.mm10.knownGene") library("clusterProfiler")
library(GenomicFeatures) library(RMariaDB) setwd("F:/ac4C_data/plot")
mm10.refseq.db \<-
makeTxDbFromGFF('F:/Genome/MusMusculus/Mus_musculus.GRCm38.100.gtf')
promoter \<- getPromoters(TxDb=mm10.refseq.db, upstream=0,
downstream=3000) peak \<-
readPeakFile("F:/ac4C_data/exomePeak/2021_11_17_exomePeak_output/con_sig_diff_peak.bed")
tagMatrix \<- getTagMatrix(peak, windows=promoter) #1 Heatmap of ChIP
binding to TSS regions tagHeatmap(tagMatrix, xlim=c(-3000, 3000),
color="red") peakHeatmap(peak, TxDb=mm10.refseq.db, upstream=0,
downstream=3000, color="blue") #2 Average Profile of ChIP peaks binding
to TSS region plotAvgProf(tagMatrix, xlim=c(0, 3000), conf=0.95,resample
= 1000, xlab="Genomic Region (5'-\>3')", ylab = "Read Count Frequency")
#3 peaks注释 peakAnno \<- annotatePeak(peak, tssRegion=c(-3000, 3000),
TxDb=mm10.refseq.db, annoDb="org.Mm.eg.db") #4 可视化基因组注释
plotAnnoPie(peakAnno) plotAnnoBar(peakAnno) vennpie(peakAnno)
upsetplot(peakAnno) #5 peak（TF结合位点）到最近的gene的TSS之间的距离
plotDistToTSS(peakAnno, title="Distribution of transcription
factor-binding loci`\nrelative `{=tex}to TSS")
