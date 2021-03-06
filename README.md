# OnTAD
OnTAD is an Optimal Nested TAD caller for Hi-C data

## Getting Started

### Prerequisites
GNU Scientific Library (https://www.gnu.org/software/gsl/)

### Installing
OnTAD is a portable application without requirement of installation. User can simply clone the github repo to get full usage.

### Examples
Call hierarchical TADs from the test matrix (http://bx.psu.edu/~lua137/OnTAD/chr18.matrix).

The test matrix is from Rao et al, Cell 2014. And it is in Gm12878 with 10kb resolution.

```
OnTAD chr18.matrix -penalty 0.1 -maxsz 200 -o OnTADraw_pen0.1_max200_meannorm_chr18.tad
```
### Results
The OnTAD output has six columns:

```
startpos  endpos  TADlevel  score1  Overlaplevel score2
```

Explanations of each field are as follows:

  startpos & endpos: the begining and end of each TAD interval
  
  TADlevel: the level of each TAD in the hierarchy. Small value denotes outter TADs and large value denotes inner TADs.
  
  score1: the confidence score.
  
  Overlaplevel & score2 are in testing and not included in the current analysis.
  
###NOTE: For all analysis in the manuscript, we used result with overlaplevel equals 0.

### Detailed Usage
```
OnTAD <Hi-C matrix> [-penalty <float>] [-maxsz <int>] [-minsz <int>] [-o output_file]
```
\<Hi-C matrix\> the n*n Hi-C contact matrix. Both raw and normalized matrix are acceptable.

-penalty \<float\> The penalty applied in scoring function to select positive TADs. Higher penalty score will result in fewer TADs.

-maxsz \<int\> The maximum size of TADs can be called. The size is determined by number of bins covered in the contact matrix.

-minsz \<int\> The minimum size of TADs can be called. The size is determined by number of bins covered in the contact matrix.

-o \<file path\> The file path for the TAD calling results.
  
### Defaults

-maxsz 200

-minsz 3

-penalty 0.1

## Versioning
Current version 1.1

## Reference
Lin An, Tao Yang, Jiahao Yang, Johannes Nuebler, Qunhua Li*, Yu Zhang*. Hierarchical Domain Structure Reveals the Divergence of Activity among TADs and Boundaries, Biorxiv 2018 (https://www.biorxiv.org/content/early/2018/07/03/361147.1)

## License
This project is licensed under the MIT License - see the LICENSE.md file for details

## Acknowledgments
This work was supported by NIH R01 GM121613 and NIH R24 DK106766 (to YZ and LA), NIH training grant T32 GM102057 (CBIOS training program to The Pennsylvania State University), a Huck Graduate Research Innovation Grant to TY, and by NIH grants R01GM109453 (to QL).

## Contact
Lin An (lua137 {at} psu {dot} edu)
