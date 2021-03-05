# mvRunKing
## Downloading mvRunKing

mvRunKing can be downloaded from https://github.com/RunKingProgram/mvRunKing.

## mvRunKing dependencies

mvRunKing runs on Linux, MAC OSX and Windows (Windows Subsystem for Linux). The runtime has the following dependencies:

C++ tool chain >= 5.5.0, GNU Science library (GSL) 2.x and zlib.

## Input Files
mvRunKing requires three main input files : genotype file, phenotype file and genomic relationship matrix (GRM) file.<br>

#### Genotype file
Genotype file consists of three PLINK BED files with the same name. For example, Genotype.bed, Genotype.bim and Genotype.fam.

#### Phenotype file
Phenotype file is a n × d matrix, which contains multiple justified phenotypes for some fixed factors including population means, stratification, sex and age so on as multiple column. Each row indicates the phenotype value for each individual in turn, in the same order as in genotype file. <br>
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


You can specify different columns of phenotypes for association tests by using “-n [num1] [num2]...[numd]”, where “-n 1 2 ” uses the original 1st and 2nd columns as phenotypes, and “-n 2 3 5” uses the 2nd, 3rd and 5th columns, and so on. 

#### GRM file
GRM file is a n × n matrix, which could be calculated by: <br>
```
./mvRunKing -bfile [Genotype] -gk 2 -o [GRM]
```
where the “-bfile [Genotype]” specifies genotype file name and “-o [GRM]” specifies output GRM name.

## Usage

mvRunKing is a command-line program. Open up a command prompt or terminal window and perform all analyses by typing commands. Software usage is very similar to GEMMA software. 

The basic usages for association analysis are:
```
./mvRunKing -bfile [Genotype] -p [Phenotype] -k [GRM] -SeparatemvRunKing -n [num1] [num2]...[numd] -o [output]

./mvRunKing -bfile [Genotype] -p [Phenotype] -k [GRM] -JointmvRunKing -n [num1] [num2]...[numd]  -o [output]

```
Where the “-SeparatemvRunKing” performs a test at once; “-JiontmvRunKing” performs Joint association analysis; “-bfile [Genotype]” specifies genotype file name; “-p [Phenotype]” specifies phenotype file name; “-k [GRM]” specifies relatedness matrix file name and “-o [output]” specifies output file name. 

## Output files
There are the two outputs from the mvRunKing: log file（output.log.txt）and Association tests(output.assoc.txt and Joint.txt).For example, output.assoc.txt:

|chr|rs|ps|n_miss|allele1|allele0|af|beta_1|beta_2|beta_3|p_afteroptimize|
| ---------- | :-----------:  | :-----------: | :-----------:| :-----------:| :-----------:| :-----------:| :-----------:| :-----------:| :-----------:| :-----------:|
|1|NC_031965.2:23571|23571|0|C|G|0.497|6.507195e-02|-1.136352e-03|-2.181224e-02|7.038245e-01|
|1|NC_031965.2:27333|27333|0|C|T|0.309|-3.645289e-02|8.535576e-02|-5.964314e-02|2.256291e-01|
|1|NC_031965.2:32667|32667|0|T|A|0.288|9.366693e-02|-1.023809e-01|5.716586e-02|8.189736e-02|
|1|NC_031965.2:37009|37009|0|A|G|0.370|-9.137052e-02|6.188948e-03|-4.190091e-02|4.415792e-01|
|1|NC_031965.2:41249|41249|0|C|T|0.187|7.633420e-02|9.230539e-02|-6.103721e-02|2.546031e-01|
|1|NC_031965.2:47701|47701|0|C|T|0.340|1.085341e-02|9.753421e-02|-1.230778e-02|3.723968e-01|


