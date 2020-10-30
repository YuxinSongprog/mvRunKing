# GEMMAX
## Downloading GEMMAX

GEMMAX can be downloaded https://github.com/YuxinSong-prog/GEMMAX.

## Input Files
GEMMAX requires three main input files : plink BED genotype file, phenotype file and relatedness matrix .PLINK 1 binary file and the structure of these files is described in http://www.cog-genomics.org/plink/1.9/formats#bed.

## Association Tests

Currently GEMMAX takes only PLINK BED types of input format.<br>
The basic usages for association analysis are:
```
./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -SeparateGEMMAX -n [num1] [num2]...[numd] -o [outputfilename]

./GEMMAX -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -JiontGEMMAX -n [num1] [num2]...[numd]  -o [outputfilename]

```
