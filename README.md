# SNVLFDR
Empirical Bayes Single Nucleotide Variant Calling for Next Generation Sequencing Data
 
 ### LFDR-based Variant Calling 
 Identifies single nucleotide variants in next-generation sequencing data by estimating their local false discovery rates. For more details, see <https://mysite.science.uottawa.ca/akarimne/wp-content/uploads/2023/12/AK-TJP-SR.pdf>.


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

#Estimated LFDRs
output$estimated.LFDRs

#Estimated proportion on non-mutant sites
output$estimated.pi0

## How to run SNVLFDR to prioritize variants called by another variant caller
bam_path <- system.file("extdata", "bam_input.csv", package="SNVLFDR")
calls_path <- system.file("extdata", "calls.vcf", package="SNVLFDR")

#Estimated LFDRs
output$estimated.LFDRs



```


## References
Karimnezhad, A and Perkins, T.J. (2023) Empirical Bayes Single Nucleotide Variant-Calling For Next-Generation Sequencing Data. Working Paper. <https://mysite.science.uottawa.ca/akarimne/wp-content/uploads/2023/12/AK-TJP-SR.pdf>
