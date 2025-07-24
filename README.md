# Phenotypic-and-Genotypic-correlation
This repository contains R code for performing genotypic and phenotypic correlation analysis using the variability package. The analysis is based on replicated multivariate trait data from different genotypes.

library(variability)
geno.corr(path_data[3:14],path_data$Trt,path_data$Rep)
pheno.corr(path_data[3:14],path_data$Trt,path_data$Rep)

##Results
> library(readxl)
> path_data <- read_excel("GENEBANK PAPERS/Cucumber paper/cucumber final.xlsx", 
+     sheet = "Sheet2")
> View(path_data)
> library(variability)
> library(variability)
> geno.corr(path_data[3:14],path_data$Trt,path_data$Rep)
$GenotypicCorrelation
     DTMF       DTFF       PTL        LL         LW         STD        DBN        LOD       
DTMF 1 **       1.0038 **  -0.17 NS   -0.29 NS   -0.1647 NS -0.4739 NS 0.2212 NS  0.0736 NS 
DTFF 1.0038 **  1 **       -0.2129 NS -0.2919 NS -0.2789 NS -0.4366 NS 0.0562 NS  -0.1837 NS
PTL  -0.17 NS   -0.2129 NS 1 **       0.9081 **  0.903 **   0.3092 NS  0.7861 **  -0.2402 NS
LL   -0.29 NS   -0.2919 NS 0.9081 **  1 **       1.1248 **  0.4728 NS  0.0443 NS  -0.4413 NS
LW   -0.1647 NS -0.2789 NS 0.903 **   1.1248 **  1 **       0.5098 NS  0.3883 NS  -0.1305 NS
STD  -0.4739 NS -0.4366 NS 0.3092 NS  0.4728 NS  0.5098 NS  1 **       0.1726 NS  0.0481 NS 
DBN  0.2212 NS  0.0562 NS  0.7861 **  0.0443 NS  0.3883 NS  0.1726 NS  1 **       -0.4209 NS
LOD  0.0736 NS  -0.1837 NS -0.2402 NS -0.4413 NS -0.1305 NS 0.0481 NS  -0.4209 NS 1 **      
PT   -0.1311 NS 0.4067 NS  -0.3581 NS 0.8035 **  0.4413 NS  -0.079 NS  0.0931 NS  -0.3192 NS
FL   -0.1121 NS -0.4121 NS 0.6364 *   1.3973 **  1.0683 **  -0.2496 NS 0.1209 NS  0.3088 NS 
FB   -0.8805 ** -1.0818 ** 0.7091 *   1.2572 **  1.1715 **  0.5252 NS  0.4227 NS  -0.4616 NS
TY   -0.2991 NS -0.5527 NS 0.7682 **  1.039 **   1.1222 **  0.6133 *   0.3621 NS  0.5408 NS 
     PT         FL         FB         TY        
DTMF -0.1311 NS -0.1121 NS -0.8805 ** -0.2991 NS
DTFF 0.4067 NS  -0.4121 NS -1.0818 ** -0.5527 NS
PTL  -0.3581 NS 0.6364 *   0.7091 *   0.7682 ** 
LL   0.8035 **  1.3973 **  1.2572 **  1.039 **  
LW   0.4413 NS  1.0683 **  1.1715 **  1.1222 ** 
STD  -0.079 NS  -0.2496 NS 0.5252 NS  0.6133 *  
DBN  0.0931 NS  0.1209 NS  0.4227 NS  0.3621 NS 
LOD  -0.3192 NS 0.3088 NS  -0.4616 NS 0.5408 NS 
PT   1 **       1.245 **   0.6681 *   0.7405 ** 
FL   1.245 **   1 **       0.6451 *   0.69 *    
FB   0.6681 *   0.6451 *   1 **       0.7216 *  
TY   0.7405 **  0.69 *     0.7216 *   1 **      

$Note1
[1] "The sig of genotypic correlation was tested using t test (two-tail). The degree of freedom used is number of genotypes - 2"

$Note2
[1] "If NaNs are produced checkout for negative genotypic variance for one or more traits"

> pheno.corr(path_data[3:14],path_data$Trt,path_data$Rep)
$PhenotypicCorrelation
     DTMF       DTFF       PTL        LL         LW         STD        DBN        LOD       
DTMF 1 **       0.7602 **  0.0093 NS  -0.2254 NS -0.1709 NS -0.3271 NS 0.1643 NS  -0.0113 NS
DTFF 0.7602 **  1 **       -0.1845 NS -0.1679 NS -0.2698 NS -0.375 *   0.0194 NS  -0.1191 NS
PTL  0.0093 NS  -0.1845 NS 1 **       0.3652 *   0.5474 **  0.187 NS   0.547 **   -0.2099 NS
LL   -0.2254 NS -0.1679 NS 0.3652 *   1 **       0.8382 **  0.2158 NS  0.1145 NS  -0.0457 NS
LW   -0.1709 NS -0.2698 NS 0.5474 **  0.8382 **  1 **       0.3424 NS  0.312 NS   -0.0804 NS
STD  -0.3271 NS -0.375 *   0.187 NS   0.2158 NS  0.3424 NS  1 **       -0.1043 NS 0.0931 NS 
DBN  0.1643 NS  0.0194 NS  0.547 **   0.1145 NS  0.312 NS   -0.1043 NS 1 **       -0.3325 NS
LOD  -0.0113 NS -0.1191 NS -0.2099 NS -0.0457 NS -0.0804 NS 0.0931 NS  -0.3325 NS 1 **      
PT   -0.0675 NS -0.1138 NS -0.0982 NS 0.2188 NS  0.2291 NS  0.1317 NS  -0.1891 NS 0.033 NS  
FL   -0.1815 NS -0.0449 NS 0.0279 NS  0.1254 NS  0.0775 NS  -0.2017 NS -0.1089 NS 0.3252 NS 
FB   -0.4545 ** -0.2579 NS 0.2049 NS  0.3159 NS  0.2829 NS  0.3304 NS  -0.0487 NS -0.1069 NS
TY   -0.1687 NS -0.2573 NS 0.161 NS   0.1165 NS  0.2759 NS  0.3238 NS  0.0918 NS  0.4472 ** 
     PT         FL         FB         TY        
DTMF -0.0675 NS -0.1815 NS -0.4545 ** -0.1687 NS
DTFF -0.1138 NS -0.0449 NS -0.2579 NS -0.2573 NS
PTL  -0.0982 NS 0.0279 NS  0.2049 NS  0.161 NS  
LL   0.2188 NS  0.1254 NS  0.3159 NS  0.1165 NS 
LW   0.2291 NS  0.0775 NS  0.2829 NS  0.2759 NS 
STD  0.1317 NS  -0.2017 NS 0.3304 NS  0.3238 NS 
DBN  -0.1891 NS -0.1089 NS -0.0487 NS 0.0918 NS 
LOD  0.033 NS   0.3252 NS  -0.1069 NS 0.4472 ** 
PT   1 **       -0.1045 NS 0.3361 NS  0.2343 NS 
FL   -0.1045 NS 1 **       0.2219 NS  0.4137 *  
FB   0.3361 NS  0.2219 NS  1 **       0.2205 NS 
TY   0.2343 NS  0.4137 *   0.2205 NS  1 **      

$Note
[1] "The sig of phenotypic correlation was tested using t test (two-tail). The degree of freedom used is (genotypes*replication) - 2"
