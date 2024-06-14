cd /d E:`\m`{=tex}6A_data`\mRNA`{=tex}\_data`\samtools`{=tex}
E:`\BIOsoft`{=tex}`\samtools-1.9`{=tex}`\samtools`{=tex}.exe view -h -@
12
E:`\m`{=tex}6A_data`\mRNA`{=tex}\_data`\STAR`{=tex}`\C1`{=tex}`\C`{=tex}1Aligned.sortedByCoord.out.bam
\> C1.sam E:`\BIOsoft`{=tex}`\samtools-1.9`{=tex}`\samtools`{=tex}.exe
index -@ 8
E:`\m`{=tex}6A_data`\mRNA`{=tex}\_data`\samtools`{=tex}`\sort`{=tex}`\C`{=tex}1.sort.bam
C1.sort.bai E:`\BIOsoft`{=tex}`\samtools-1.9`{=tex}`\samtools`{=tex}.exe
sort -@ 8
E:`\m`{=tex}6A_data`\mRNA`{=tex}\_data`\STAR`{=tex}`\C1`{=tex}`\C`{=tex}1Aligned.sortedByCoord.out.bam
-o C1.sort.bam
