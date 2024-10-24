# Bearded_CKMR
Welcome to a github repository housing data, code, and online supplements for conducting a close-kin mark-recapture analysis of the Beringia distinct population segment of bearded seals.

This repository is associated with the paper 

"Estimating Demographic Parameters for Bearded Seals, Erignathus barbatus, in Alaska using Close-Kin Mark-Recapture Methods" by B.D. Taras, P.B. Conn, M.V. Bravington L. Quakenbush, 
A. Kilian, A.R. Lang, A. Bryan, and R. Stimmelmayr.  Evolutionary Applications (In press).

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


