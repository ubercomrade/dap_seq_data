# Re-analysed data 

The origin data was obtained in reasearch "Cistrome and Epicistrome Features Shape the Regulatory DNA Landscape" [1]

## Methods

The raw data was downloaded from the NCBI GEO database (GSE60143). All sequencing data were processed from reads to peaks with snakePipes (v. 2.5.6) [2]. Reads were mapped to the TAIR10 genome with the following parameters of snakePipes “DNA-mapping tair10 -i {input.dir} -o {output.dir} --dedup --mapq 3”. bowtie2 was the default tool for alignment. Peak calling was done using snakePipes with following parameters “ChIP-seq -d {dir.with.DNA-mapping.results} --peakCaller MACS2 tair10 TABLE.yaml --peakCallerOptions "--qvalue 0.001"”, parametres “--singleEnd or --pariedEnd” also was used depend on data. TABLE.yaml was constructed as described in https://snakepipes.readthedocs.io/en/latest/content/workflows/ChIP-seq.html. For all samples was used control SRR2926068 or SRR2926069 depend on data type.

## Reference

 [1] Ronan C. O’Malley, Shao-shan Carol Huang, Liang Song, Mathew G. Lewsey, Anna Bartlett, Joseph R. Nery, Mary Galli, Andrea Gallavotti, and Joseph R. Ecker (2016). Cistrome and Epicistrome Features Shape the Regulatory DNA Landscape, Cell. 2016 May 19;165(5):1280-92. doi: 10.1016/j.cell.2016.04.038. 

 [2] Vivek Bhardwaj, Steffen Heyne, Katarzyna Sikora, Leily Rabbani, Michael Rauer, Fabian Kilpert, Andreas S Richter, Devon P Ryan, Thomas Manke, snakePipes: facilitating flexible, scalable and integrative epigenomic analysis, Bioinformatics, Volume 35, Issue 22, 15 November 2019, Pages 4757–4759, https://doi.org/10.1093/bioinformatics/btz436