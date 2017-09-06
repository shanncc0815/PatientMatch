# PatientMatch

# Dataset: cleanDataset_1M_withQuote.csv
# Copy over cleanDataset_1M_withQuote.csv and PHONE_dict.RData @ https://drive.google.com/drive/folders/0B9IpfpvY8BnecTJWODhxUG00VkE to meta/ subfolder
# PHONE_dict.RData contain all mapping of EnterpriseID and different PHONE/PHONE2 numbers

# Candidate list
## pmc4_submit031_54672TP_0FP.csv
## pmc4_submit034_Vote200g0_57725Pairs_57106TP_619FP.csv
## pmc4_submit035(submit034_diff_submit031)_3053Pairs_2434TP_619FP.csv
## pmc4_submit036_Vote200_56275Pairs_56229TP_46FP.csv
## pmc4_submit037(submit036_diff_submit031)_1603Pairs_1557TP_46FP.csv

# Summary spreadsheet to calculate Precision Recall
## PatientMatching_PrecisionRecall_0906_2017.xls

# Utility code to compare pairs: Utility/Pair_Utility.r
# Example code:  Examine_Overlap_v5_0906.r (Demonstrate how to use diffPair and combinePair
# run 'Rscript Examine_Overlap_v5_0906.r' in linux bash or source("Examine_Overlap_v5_0906.r") in R

# Run Clustering to rank candidate list
# Example code:  RL_Clustering_FP_v5_0906.r
# run 'Rscript RL_Clustering_FP_v5_0906.r' in linux bash or source("RL_Clustering_FP_v5_0906.r") in R 

# Goal 1: Identify 46 FP pairs in the following list:
## Examine_EpiClustering_jarowinkler_pmc4_submit037(submit036_diff_submit031)_1603Pairs_1557TP_46FP.csv

# Goal 2: Identify 619 FP in the following list:
## Examine_EpiClustering_jarowinkler_pmc4_submit035(submit034_diff_submit031)_3053Pairs_2434TP_619FP.csv

# Goal 3: Combine the clean set with "pmc4_submit031_54672TP_0FP.csv", which will give us 54672+2434 = 57106 pairs of TP 
## Total # TP pairs = 57482 => Still have 376 FNs

# Goal 4: Write a script to consider 3-way matching
# i.e. If A==B, A==C, B must be paired with C.  However, B==C may be missed due to the candidate pairs was not generated at the first place.

