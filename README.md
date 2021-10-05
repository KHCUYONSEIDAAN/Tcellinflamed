# Tcellinflamed
A major issue in immune checkpoint inhibitor is a lack of efficacy. Previous studies reported that T cell inflamed signature can help to predict immunotherapy response. Many studies have been conducted to investigate mechanisms of immunotherapy resistance by defining tumor microenvironment as T cell inflamed and non-T cell inflamed subsets. Although calculation method of T cell inflamed subsets exists, valid screening tools for distinguishing T cell inflamed from non-T cell inflamed subsets using gene expression data are still needed. Previous studies suggested that scoring method which distinguish non-T cell inflamed, T cell inflamed and intermediate based on gene expression data(Luke et al., 2019)(Spranger et al., 2016). However, general researchers who are unfamiliar with detailed calculation of equation can have analysis difficulties in using scoring formula. In this reason, we recently developed R package that predict T cell inflamed tumors with RNA seq expression data. Tcellinflamed_Function is the first package to detect T cell inflamed subset to help interpret cancer gene expression data. This package will be beneficial to distinguish T cell inflamed hot tumor and Non-T cell inflamed cold tumor to optimize selection of right patients who will benefit from ICIs. This package will be beneficial to distinguish T cell inflamed hot tumor and Non-T cell inflamed cold tumor to optimize selection of right patients who will benefit from ICIs.  


# Installation and Usage
<br> library(devtools)
<br> library(Tcellinflamed)
<br> # you can download the Tcellinflamed.tar.gz file in your local pc folder
<br> install.packages("C:\\Tcellinflamed\\Tcellinflamed.tar.gz",repos=NULL, type="source") 
<br> library(Tcellinflamed)
<br> setwd("C:\\Tcellinflamed\\")
<br> inputfilelist<-read.csv("C:\\Tcellinflamed\\inputfile_example.csv")
<br> Tcellinflamed_Function(Inputfile, Numberofgenes)


# Inputfile	
Users can simply use log CPM file(csv) which contains T cell relative Genes(row name) and it's expressions
<br> Example file is available in the https://github.com/KHCUYONSEIDAAN/Tcellinflamed/ 
<br> Using nrow(inputfile) code, users can easily generate the result files. or users can write number of testing genes (T cell relative genes). 

# Author(s)
San-Duk Yang, Hyun-Seok Park, Sun-Min Lim, Byoung Chul Cho (Yonsei Cancer Research Institute, DAAN Therapeutics)

# Examples
Tcellinflamed_Function(a.csv,nrow(inputfile))
