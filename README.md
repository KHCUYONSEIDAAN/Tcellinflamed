# Tcellinflamed
It is important to distinguish the T cell inflamed Tumor types(Hot tumor) and non-T cell inflamed tumor types(Cold Tumor) for successful cancer immuno-therapy. This function distinguish the T cell inflamed, Non T cell inflamed, Intermediate phenotype in the cancer RNA sequencing data. Tcellinflamed_Function is the package to detect T cell inflamed subset to help interpret cancer gene expression data.This package will be beneficial to distinguish T cell inflamed hot tumor and Non-T cell inflamed cold tumor to optimize selection of right patients who will benefit from ICIs.  
# Usage
Tcellinflamed_Function(Inputfile, Numberofgenes)
# Arguments
# Inputfile	
You can simply use log CPM file(csv) which contains T cell relative Genes(row name) and it's expressions
# Numberofgenes	
You can write number of testing genes (upper T cell relative genes).

# Author(s)
San-Duk Yang, Hyun-Seok Park, Sun-Min Lim, Byoung Chul Cho (Yonsei Cancer Research Institute, DAAN Therapeutics)

# Examples
Tcellinflamed_Function(a.csv,nrow(inputfile))
