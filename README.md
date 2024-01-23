# SNVLFDR
Empirical Bayes Single Nucleotide Variant Calling for Next Generation Sequencing Data
 
 ### LFDR-based Variant Calling 
 Identifies single nucleotide variants in next-generation sequencing data by estimating their local false discovery rates. For more details, see <https://doi.org/10.1038/s41598-024-51958-z>.


## Installation

The package can be installed from the GitHub repository
```r
devtools::install_github("empiricalbayes/SNVLFDR")
```

## Getting Started
You can load SNVLFDR as follows:

```r
library(SNVLFDR)
```

## How to run SNVLFDR to call variants on an example data.
```r
bam_input <- system.file("extdata", "bam_input.csv", package="SNVLFDR")
bedfile <- system.file("extdata", "regions.bed", package="SNVLFDR")
BQ.T=20
MQ.T=20
pi0.initial=0.95
AF.T=0.01
DP.T=10
LFDR.T=0.01
error=NULL
method='empirical'
epsilon=0.01
output=get_LFDRs(bam_input,bedfile,BQ.T,MQ.T,pi0.initial,AF.T,DP.T,LFDR.T,error,method,epsilon)

#Estimated LFDRs
output$estimated.LFDRs

#Estimated proportion on non-mutant sites
output$estimated.pi0

#Filtered Bam matrix that includes estimated LFDRs
output$filtered.bam


## How to run SNVLFDR to prioritize variants called by another variant caller
bam_path <- system.file("extdata", "bam_input.csv", package="SNVLFDR")
calls_path <- system.file("extdata", "calls.vcf", package="SNVLFDR")
output=get_LFDRs_given_caller(bam_input=bam_path,calls=calls_path,LFDR.T=0.01,error=NULL)

#Updated VCF file that includes estimated LFDRs
output$updated.vcf


```


## References
Karimnezhad, A and Perkins, T.J. (2024) Empirical Bayes single nucleotide variant-calling for next-generation sequencing data. Scientific Reports 14,  1550, <https://doi.org/10.1038/s41598-024-51958-z>
