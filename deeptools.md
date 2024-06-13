cd /media/sf_F\_DRIVE/ac4C_data/deeptools
/home/manager/miniconda3/bin/multiBamSummary bins -b
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_C1.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_C2.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK1.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK2.bam -o IP.npz

/home/manager/miniconda3/bin/multiBamSummary bins -b
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/C1.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/C2.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/MK1.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/MK2.bam -o mRNA.npz

/home/manager/miniconda3/bin/multiBamSummary bins -b
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/C1.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/C2.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/MK1.bam
/media/sf_E\_DRIVE/ac4C_data/mRNA/samtools/sort/MK2.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_C1.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_C2.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK1.bam
/media/sf_E\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK2.bam -o
total.npz

cd /media/sf_E\_DRIVE/ac4C_data/deeptools
/home/manager/miniconda3/bin/plotCorrelation -in IP.npz -o
IP_heatmap.png --corMethod pearson -p heatmap --skipZeros --plotTitle
"Pearson Correlation of Read Counts" --whatToPlot heatmap --plotNumbers
--removeOutliers -o IP_heatmap.png
/home/manager/miniconda3/bin/plotCorrelation -in IP.npz -o
mRNA_heatmap.png --corMethod pearson -p heatmap --skipZeros --plotTitle
"Pearson Correlation of Read Counts" --whatToPlot heatmap --plotNumbers
--removeOutliers -o mRNA_heatmap.png
/home/manager/miniconda3/bin/plotCorrelation -in total.npz -o
total_heatmap.png --corMethod spearman -p heatmap --skipZeros
--plotTitle "spearman Correlation of Read Counts" --whatToPlot heatmap
--plotNumbers --removeOutliers -o total_heatmap.png

/home/manager/miniconda3/bin/plotFingerprint -b
/media/sf_F\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK1.bam
/media/sf_F\_DRIVE/ac4C_data/ac4C/samtools/sort/ac4C_MK2.bam
/media/sf_F\_DRIVE/ac4C_data/mRNA/samtools/sort/MK1.bam
/media/sf_F\_DRIVE/ac4C_data/mRNA/samtools/sort/MK2.bam --labels
ac4C_MK1 ac4C_MK2 MK1 MK2 --minMappingQuality 30 --skipZeros
--numberOfSamples 50000 -T "Fingerprints of MK801" --plotFile
fingerprints_MK.eps --outRawCounts fingerprints.tab
