# Bearded_CKMR
Welcome to a github repository housing data and code to conduct close-kin mark-recapture estimation of bearded seals in Alaska.
This repository is associated with the paper 

Using Close-Kin Mark-Recapture Methods to Estimate Demographic Parameters Critical for Managing the Bearded Seal, 
Erignathus barbatus, a Harvested Species Listed under the U.S. Endangered Species Act by B.D. Taras, P.B. Conn, M.V. Bravington L. Quakenbush, 
A. Kilian, A.R. Lang, A. Bryan, and R. Stimmelmayr.  To be submitted to Evolutionary Applications.

## Data
The Bearded_CKMR/data directory includes data necessary to conduct CKMR analysis using bearded seal data.
The files there include

-Maturity.csv: This table provides information on sexual maturity of ice seals in Alaska (from Conn and Trukhanova 2023)
-MHS_matches.csv: This table defines maternal half-sibling / grandparent-grandchild pairs; the row indices provided index different rows in Samples.csv
-PHS_matches.csv: Same as above, but for paternal half-sibling pairs.
-POP_matches.csv: Same as above, but for parent-offspring pairs
-Reproduction_table.csv: This table provides female fecundity schedules for ice seals in Alaska (from Conn and Trukhanova 2023)
-Samples.csv: This table provides data for all bearded seals successfully genotyped, inclding age, sex, date of harvest, and location of harvest
-Spring_pups_info.csv: This table provides information on individuals used to resolve age of pups relative to our assumed population model age increment
-Survival_ests.csv: This table provides natural mortality estimates for ice seals in Alaska, including bearded seals (from Trukhanova et al. 2018)

## Analysis 
There are two steps in conducting CKMR analysis of bearded seal data.  First, raw bearded seal data are 
input and formatted - and discrepancies and missing data are reconciled using the .Rmd in Bearded_CKMR/inst/CKMR_data_formatting.Rmd.
This produces an environment object "CKMR_sample_data.RData" which is read in by the actual analysis script.

The analysis itself, including sensitivities, is conducted in the R markdown file "CKMR_modeling.Rmd", calling TMB source code that is 
located in the /src directory.
