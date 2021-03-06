# Biostatistics

##problem 1
This dataset is drawn from 300,000 primary physician visits in Brazil across 2014 
and 2015. The information about the appointment was automatically coded when the 
patient scheduled the appointment and then the patient was marked as having either 
attended or not. The information about the appointment included demographic data, time 
data, and conditions concerning the reason for the visit.
##################################################################
##problem 2
Explore the data:
Show the type of the data and assign each of feature, phenotype and expression data to
different variables
1.a Show the type of each column
1.b Show column names and rows name
1.c Calculate summary of each column
1.d Show frequency of categorical data, taking into the consideration, NA values frequency if
any.
1.e Calculate the correlation and covariance between the first 10 columns only of our data set
and draw full correlation matrix.
1.f For both genes: GSM95478,GSM95473 show the plot with a line of their relation.
=> Question 2:
Using PCA and SVD, Prove by plotting and values that both can return the same result by
suitable normalization.
=>Question 3:
256 visual artists were surveyed to find out their zodiac sign. The results were: Aries (29),
Taurus (24), Gemini (22), Cancer (19), Leo (21), Virgo (18), Libra (19), Scorpio (20), Sagittarius
(23), Capricorn (18), Aquarius (20), Pisces (23).
3.1) Test the hypothesis that zodiac signs are evenly distributed across visual artists.
3.2) Explicitly mention your H1 and Ho assumption.
=> Question 4:
Plot hierarchical clusters on our first 10 columns of edata and apply the kmeans to all the edata
columns and show the centroid of the result.
Setups to Download Data:
1- Install bioconductor (refer to the labs in this step)
2- Install antiProfilesData By BiocManager::install("antiProfilesData")
3- To Access our data use antiProfilesData::apColonData

################################################################33
##problem 3
The dataset
Breast Cancer Proteomes Dataset
Breast Cancer is a multifactorial disease that forms in the cells of the breast. Breast cancer can occur in both men and women, but it's far more common in women.
Dataset Description 
This data set contains published iTRAQ proteome profiling of 77 breast cancer samples generated by the Clinical Proteomic Tumor Analysis Consortium (NCI/NIH). It contains expression values for ~12.000 proteins for each sample, with missing values present when a given protein could not be quantified in a given sample.
This dataset consist of 3 tables: 
1)	77_cancer_proteomes_CPTAC_itraq.csv
This table includes protein expression values and metadata on 12553 genes from 80 breast cancer patients and 3 healthy individuals.
???	RefSeqaccessionnumber: RefSeq protein ID (each protein has a unique
ID in a RefSeq database)
???	gene_symbol: a symbol unique to each gene (every protein is encoded
by some gene)
???	gene_name: a full name of that gene
Remaining columns: log2 iTRAQ ratios for each sample (protein
expression data, most important), three last columns are from healthy
individuals
2)	clinical_data_breast_cancer.csv
This table contains clinical data and various breast cancer classifications from 105 breast cancer patients
???	First column "Complete TCGA ID" is used to match the sample IDs in the main cancer proteomes file
???	Other columns contain data about the cancer classification of a given sample using different methods

3)	PAM50_proteins.csv
This table contains the list of genes and proteins used by the PAM50 classification system. The column RefSeqProteinID contains the protein IDs that can be matched with the IDs in the main protein expression data set.

Part1: Data preprocessing 
1.1.Subset the columns of proteomes table. As you learned about genomic datasets you will find: 
-	The columns in proteomes table represent patients samples 
-	The rows in clinical data table also represent patients samples
You will find that number of columns don???t match so you need to subset the data in both proteomes table and clinical data table to keep the data of patient samples that exist in both tables. (Like inner join in DBs)
Note:  you will find that the IDs in the two tables don???t have the same format so you will need to find a way to match the formats. 
1.2.	Subset the rows of proteomes table by removing rows with missing values
