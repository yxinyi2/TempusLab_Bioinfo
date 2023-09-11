# TempusLab_Bioinfo

This repository contains my solution for the coding challenge for the Bioinformatics Scientist Position at Tempus Lab. In this README, I will provide an overall descrption, my approch and a description for the results

## Description
This is a annotation tool developed to annotate each variant in a VCF file. For each variant, the following fields are annotated:
1. Depth of sequence coverage at the site of variation.
2. Number of reads supporting the variant.
3. Percentage of reads supporting the variant versus those supporting reference reads.
4. Type of variation, their effect and the minor allele frequency of the variant if available.

## Approach
To annotate the variants, I first re-structured the input VCF file into a data frame using a R package called 'vcfR'. Depth of sequence coverage at the site of variation is annotated using NR(Number of reads covering variant location in this sample) in the FORMAT field. Number of reads supporting the variant is annoated using NV(Number of reads containing variant in this sample) in the FORMAT field. Percentage of reads supporting the variant versus those supporting reference reads is calculated by NV/NR. To annotate the type of variation, their effect and the minor allele frequency, I created an API endpoint for each variant, and get the corresponding information if available.

## Result
A csv file is generated that contains all the annotated variants. 
