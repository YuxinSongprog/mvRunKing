# GEMMAX
## Downloading GEMMAX

GEMMAX can be downloaded https://github.com/YuxinSong-prog/GEMMAX.

## Input Files
GEMMAX requires three main input files : plink BED genotype file, phenotype file and relatedness matrix .<br>
#### PLINK BED genotype file
PLINK 1 binary file and the structure of these files is described in http://www.cog-genomics.org/plink/1.9/formats#bed. 
#### Phenotype file
Phenotype file, as the same order as PLINK genotype file, contains phenotype information. One can include multiple phenotypes as multiple columns in the phenotype file. <br>
#### Relatedness matrix file
Relatedness matrix is a  n × n matrix, where each row and each column corresponds to individuals in the same order as in the *.fam file or in the mean genotype file, and ith row and jth column is a number indicating the relatedness value between ith and jth individuals. <br>

## Association Tests

Currently GEMMAX takes only PLINK BED types of input format. We can specify a different column for association tests by using “-n [num]”, where “-n 1” uses the original first column as phenotypes, and “-n 2” uses the second column, and so on. 

The basic usages for association analysis are:
```
./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -SeparateGEMMAX -n [num1] [num2]...[numd] -o [outputfilename]

./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -JiontGEMMAX -n [num1] [num2]...[numd]  -o [outputfilename]

```
