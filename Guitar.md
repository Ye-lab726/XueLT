rm(list=ls()) options(stringsAsFactors = F)

library(Guitar) stBedFiles \<-
list("E:/ac4C_data/ac4C/bedtools/ac4C_C1.bed") stBedFiles \<-
list("E:/ac4C_data/exomePeak/2021_11_17_exomePeak_output/2021_11_17-exomePeak_output_2sample/con_sig_diff_peak.bed")
txdb \<- makeTxDbFromGFF(file =
"E:/Genome/MusMusculus/Mus_musculus.GRCm38.100.gtf.gz", format="gtf",
dataSource="Ensembl", organism="Mus musculus")

gc() p \<- GuitarPlot(txTxdb = txdb, stBedFiles = stBedFiles, headOrtail
= FALSE, enableCI = FALSE, mapFilterTranscript = TRUE, pltTxType =
c("mrna"), stGroupName = "ac4C_peak")

p \<- p + ggtitle(label = "Distribution on mRNA") + theme(plot.title =
element_text(hjust = 0.5)) + theme_bw() write.csv(p,"p.csv")
