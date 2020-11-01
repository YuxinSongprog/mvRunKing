# GEMMAX
## Downloading GEMMAX

GEMMAX can be downloaded https://github.com/YuxinSong-prog/GEMMAX.

## Input Files
GEMMAX requires three main input files : PLINK BED genotype file, phenotype file and relatedness matrix .<br>
#### PLINK BED genotype file
PLINK 1 binary file and the structure of these files is described in http://www.cog-genomics.org/plink/1.9/formats#bed. 
#### Phenotype file
Phenotype file, as the same order as genotype file, contains phenotype information. One can include multiple phenotypes as multiple columns in the phenotype file. <br>
#### Relatedness matrix file
Relatedness matrix is a  n × n matrix, where each row and each column corresponds to individuals in the same order as in the .fam file or in the mean genotype file, and ith row and jth column is a number indicating the relatedness value between ith and jth individuals. <br>

## Association Tests

Currently GEMMAX takes only PLINK BED types of input format. You can specify different columns of phenotypes for association tests by using “-n [num1] [num2]...[numd]”, where “-n 1 2 ” uses the original 1st and 2nd columns as phenotypes, and “-n 2 3 5” uses the 2nd, 3rd and 5th columns, and so on. 

The basic usages for association analysis are:
```
./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -SeparateGEMMAX -n [num1] [num2]...[numd] -o [outputfilename]

./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -JiontGEMMAX -n [num1] [num2]...[numd]  -o [outputfilename]

```
