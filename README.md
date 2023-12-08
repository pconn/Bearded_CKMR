# Bearded_CKMR
Welcome to a github repository housing data, code, and online supplements for conducting a close-kin mark-recapture analysis of the Beringia distinct population segment of bearded seals.

This repository is associated with the paper 

Using Close-Kin Mark-Recapture Methods to Estimate Demographic Parameters Critical for Managing the Bearded Seal, 
Erignathus barbatus, a Harvested Species Listed under the U.S. Endangered Species Act by B.D. Taras, P.B. Conn, M.V. Bravington L. Quakenbush, 
A. Kilian, A.R. Lang, A. Bryan, and R. Stimmelmayr.  To be submitted to Evolutionary Applications.

## Data
The Bearded_CKMR/data directory includes data necessary to conduct CKMR analysis using bearded seal data.
The files there include

- bearded_genos.csv: This file is a comma delimited text file consisting of a 1484 x 5139 table of genotypes for 1484 bearded seals.  The first column is an individual identifier, while remaining columns give alleles.  The column names represent combinations of loci and allele number (e.g., L10006.1 and L10006.2 represent alleles 1 and 2 at locus L10006, respectively).  The possible alleles at each loci are 'A', 'B', or null ('0')
- Maturity.csv: This table provides information on sexual maturity of ice seals in Alaska (from Conn and Trukhanova 2023)
- MHS_matches.csv: This table defines maternal half-sibling / grandparent-grandchild pairs; the row indices provided index different rows in Samples.csv
- PHS_matches.csv: Same as above, but for paternal half-sibling pairs.
- POP_matches.csv: Same as above, but for parent-offspring pairs
- Reproduction_table.csv: This table provides female fecundity schedules for ice seals in Alaska (from Conn and Trukhanova 2023)
- Samples.csv: This table provides data for all bearded seals successfully genotyped, inclding age, sex, date of harvest, and location of harvest
- Spring_pups_info.csv: This table provides information on individuals used to resolve age of pups relative to our assumed population model age increment
- Survival_ests.csv: This table provides natural mortality estimates for ice seals in Alaska, including bearded seals (from Trukhanova et al. 2018)

## Analysis 
There are two steps in conducting CKMR analysis of bearded seal data.  First, raw bearded seal data are 
input and formatted - and discrepancies and missing data are reconciled using the .Rmd in Bearded_CKMR/inst/CKMR_data_formatting.Rmd.
This produces an environment object "CKMR_sample_data.RData" which is read in by the actual analysis script.

The analysis itself, including sensitivities, is conducted in the R markdown file "CKMR_modeling.Rmd", calling TMB source code that is 
located in the /src directory.

## Supplements

We include several supplements relevant to our CKMR analysis in the /supplements folder.  These include

- Supplement_1.csv  This table gives locations and accession numbers of the bearded seal samples used in genotyping
- Supplement_2.pdf  This file describes our DNA sampling protocols
- Supplement_3.pdf  This document describes how the probabilities of grandparent-grandchild kin pairs were derived
- Supplement_4.csv  This large table gives bearded seal genotypes.  Each individual is represented by a row, while each 2 column pairs represents a different locus.  For instance; L252.1 and L252.2 represent the two alleles found at locus 251.  Possible alleles are 'A', 'B' and '0' (null)
- Supplement_5.csv  This table provides sample information for each kin pair match
