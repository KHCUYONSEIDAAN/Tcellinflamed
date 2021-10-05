# Tcellinflamed
A major issue in immune checkpoint inhibitor is a lack of efficacy. Previous studies reported that T cell inflamed signature can help to predict immunotherapy response. Many studies have been conducted to investigate mechanisms of immunotherapy resistance by defining tumor microenvironment as T cell inflamed and non-T cell inflamed subsets. Although calculation method of T cell inflamed subsets exists, valid screening tools for distinguishing T cell inflamed from non-T cell inflamed subsets using gene expression data are still needed. Previous studies suggested that scoring method which distinguish non-T cell inflamed, T cell inflamed and intermediate based on gene expression data(Luke et al., 2019)(Spranger et al., 2016). However, general researchers who are unfamiliar with detailed calculation of equation can have analysis difficulties in using scoring formula. In this reason, we recently developed R package that predict T cell inflamed tumors with RNA seq expression data. Tcellinflamed_Function is the first package to detect T cell inflamed subset to help interpret cancer gene expression data. This package will be beneficial to distinguish T cell inflamed hot tumor and Non-T cell inflamed cold tumor to optimize selection of right patients who will benefit from ICIs. This package will be beneficial to distinguish T cell inflamed hot tumor and Non-T cell inflamed cold tumor to optimize selection of right patients who will benefit from ICIs.  

# Tcell inflamed relative gene signature 
Established gene signatures were referenced by Gajewski T cell-inflamed signature, IFN-gamma related signature, T cell effector signature and Immune cytolytic activity signature(Luke et al., 2019)(Spranger et al., 2016). 

# Installation and Usage
<br> library(devtools)
<br> library(Tcellinflamed)
<br> # Users can download Tcellinflamed_Function: https://github.com/KHCUYONSEIDAAN/Tcellinflamed/blob/main/Tcellinflamed.tar.gz 
<br> install.packages("C:\\Tcellinflamed\\Tcellinflamed.tar.gz",repos=NULL, type="source") 
<br> library(Tcellinflamed)
<br> setwd("C:\\Tcellinflamed\\")

<br> # Users can extract T cell effector gene subset 
<br> inputfile<-read.csv("D:\\Tcellinflamed\\TCGA-LUAD_tumoronly_lcpm.csv")
<br> CTL<-c("GZMA","PRF","GZMB","PRF1","EOMES","IFNG","TNF","CXCL9","CXCL10","CD8A","CD4","FOXP3","ICOS","CTLA4","IRF1","CCL2","CCL3","CCL4","GZMK","HLA.DMA","HLA.DMB","HLA.DOA","HLA.DOB","CCL5","CD27","CD274","PDCD1LG2","CD276","CMKLR1","CXCR6","HLA.DQA1","HLA.DRB1","HLA.E","IDO1","LAG3","NKG7","PSMB10","STAT1","TIGIT")
<br> Tcellgene<-inputfile$Gene %in% CTL
<br> inputfilelist<-inputfile[Tcellgene,]
<br> write.csv(inputfilelist,"D:\\Tcellinflamed\\inputfile_example.csv",row.names=FALSE)

<br> inputfilelist<-read.csv("C:\\Tcellinflamed\\inputfile_example.csv")
<br> Tcellinflamed_Function(Inputfile, Numberofgenes)
<br> # How can extract T cell inflamed subset(Tcellinflamed_Function input) in your expression file 


# Inputfile	
Users can simply use log CPM file(csv) which contains T cell relative Genes(row name) and it's expressions
<br> Example file is available in the https://github.com/KHCUYONSEIDAAN/Tcellinflamed/blob/main/inputfile_example.csv
<br> Using nrow(inputfile) code, users can easily generate the result files. or users can write number of testing genes (T cell relative genes). 

# Author(s)
San-Duk Yang, Hyun-Seok Park, Sun-Min Lim, Byoung Chul Cho (Yonsei Cancer Research Institute, DAAN Therapeutics)

# Examples
Tcellinflamed_Function(a.csv,nrow(inputfile))

# Reference
<br> Jiang,P. et al. (2018) Signatures of T cell dysfunction and exclusion predict cancer immunotherapy response, Nat Med, 24, 1550–1558.
<br> Luke,J.J. et al. (2019) WNT/β-catenin pathway activation correlates with immune exclusion across human cancers, Clin Cancer Res, 25(10), 3074–3083.
<br> Spranger,S. et al. (2016) Density of immunogenic antigens does not explain the presence or absence of the T-cell–inflamed tumor microenvironment in <br> melanoma, PNAS, 113 (48), E7759-E7768.
<br> Ayers,M. et al. (2017) IFNgamma-related mRNA profile predicts clinical response to PD-1 blockade. J Clin Invest,127, 2930–40.
<br> Spranger,S. et al. (2019) Melanoma-intrinsic beta-catenin signalling prevents anti-tumour immunity. Nature,523, 231–5.
<br> Herbst,R.S. et al. (2014) Predictive correlates of response to the anti-PD-L1 antibody MPDL3280A in cancer patients. Nature, 515, 563–7.
<br> Rooney,M.S. et al. (2015) Molecular and genetic properties of tumors associated with local immune cytolytic activity. Cell, 160, 48–61.
<br> Shah, S. et al. (2016) Clinical Response of a Patient to Anti–PD-1 Immunotherapy and the Immune Landscape of Testicular Germ Cell Tumors, Cancer Immunol. Res.1158, 2326-6066. 
