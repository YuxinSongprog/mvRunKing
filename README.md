# mvRunKing
## Downloading mvRunKing

mvRunKing can be downloaded from https://github.com/RunKingProgram/mvRunKing.

## mvRunKing dependencies

mvRunKing runs on Linux, MAC OSX and Windows (Windows Subsystem for Linux). The runtime has the following dependencies:

C++ tool chain >= 5.5.0, GNU Science library (GSL) 2.x and zlib.

## Input Files
mvRunKing requires three main input files : genotype file, phenotype file and relatedness matrix file.<br>

#### Genotype file
Genotype file consists of three PLINK BED files with the same name. For example, Genotype.bed, Genotype.bim and Genotype.fam.

#### Phenotype file
Phenotype file that only contains phenotypic variates which should to be adjust for all covariates, and the order of individuals should be the same as genotype file. One should include multiple correlated phenotypes in multiple columns in the phenotype file. Here is an example of the header and first 8 rows for the *d*  phenotypes:  <br>
|phenotype 1| phenotype 2| phenotype 3|...|phenotype d|
| ---------- | :-----------:  | :-----------: | :-----------:| :-----------:|
|1 |4.9| 1.1|...|2.3|
|1.1 |4.6| 2.2|...|2.4|
|1.2 |8| 3.8|...|2.2|
|2.1 |10.1| 1.3|...|3.2|
|3.1 |14.9| 1.4|...|3.2|
|3.1 |16.2| 2.7|...|2.3|
|3.2 |15.2| 3.6|...|2.3|
|3 |14.3| 4.5|...|4.2|
...
#### Relatedness matrix file
Relatedness matrix is a  n × n matrix, where each row and each column corresponds to individuals in the same order as in the .fam file, and *i*th row and *j*th column is a number indicating the relatedness value between *i*th and *j*th individuals. <br>

## Running mvRunKing

mvRunKing is a command-line program. Open up a command prompt or terminal window and perform all analyses by typing commands. Software usage is very similar to GEMMA software. 

The basic usages for association analysis are:
```
./mvRunKing -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -SeparatemvRunKing -n [num1] [num2]...[numd] -o [outputfilename]

./mvRunKing -bfile [plinkfile] -p [phenofile] -k [kinshipfile] -JiontmvRunKing -n [num1] [num2]...[numd]  -o [outputfilename]

```
Where the “-SeparatemvRunKing” performs a test at once; “-JiontmvRunKing” performs Joint association analysis; “-bfile [plinkfile]” specifies PLINK BED files prefix; “-p [filename]” specifies phenotype file name; “-k [kinshipfile]” specifies relatedness matrix file name and “-o [outputfilename]” specifies output file prefix. You can specify different columns of phenotypes for association tests by using “-n [num1] [num2]...[numd]”, where “-n 1 2 ” uses the original 1st and 2nd columns as phenotypes, and “-n 2 3 5” uses the 2nd, 3rd and 5th columns, and so on. 
