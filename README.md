# Code for a database of group actions on Riemann surfaces

This repository hosts code used to compute the data found at www.lmfdb.org/HigherGenus/C/Aut/.  This data classifies groups acting on Riemann surfaces.


To run this code, first open the file `main.mag` in an editor and set the genus you wish to run by searching and replacing “xx” with the genus: some number between 02-10. There are 8 places where 'xx' appears in the document (one is inside a comment).

Be sure a copy of the file  https://github.com/jenpaulhus/breuer-modified/blob/master/genvectors.mag is in the folder also.

Then start Magma and type:
`load “main.mag”;`

The data will be written to a file called `gxxfinaldata`


Sample Output
------------------

The data in the file `gxxfinaldata` will have entries for each possible group action, up to simultaneous conjugation, separated by the '@' symbol. Depending on whether the action represents the full automorphism group,  the entries will have one of the following two possible organizations.  

1. If the entry represents the full automorphism group it will have the format: 
   + group  as ordered pair [n,d] representing SmallGroup(n,d)<br>
   + signature<br>
   + conjugacy classes for this refined passport, listed as in Magma<br>
   + ordered pair representing which list of possible conjugacy classes for this group and signature the action comes from (as computed in `generate_ccnums.mag`)<br>
   + r lists of integers representing the r generating vectors as permutations<br>
   + HY or HN representing if the action is hyperelliptic or not<br>
   + (optional) if HY on the previous line,  a list of integers representing the hyperelliptic involution as a permutation<br>
   + (optional) if HY on the line two previously, equation(s) for the curve(s) in LaTeX form <br>
   + CY or CN representing if cyclic trigonal or not<br>
   + (optional) if CY on the previous line, a list of integers representing the trigonal automorphism as a permutation<br><br>
For example, in genus 3 there is a family of hyperelliptic curves with automorphism group SmallGroup(32,9) and signature [0;2,4,8].  One of the actions corresponds to conjugacy classes [6,10,12] and its entry in the file g03finaldata looks like: <br><br>
 `[32,9]`<br>
`[ 0, 2, 4, 8 ]`<br>
`[ 6, 10, 12 ]`<br>
`[ 7, 1 ]`<br>
`[ 11, 12, 9, 10, 16, 15, 14, 13, 3, 4, 1, 2, 8, 7, 6, 5, 27, 28, 25, 26, 32, 31, 30, 29, 19, 20, 17, 18, 24, 23, 22, 21 ]`<br>
`[ 20, 19, 18, 17, 23, 24, 21, 22, 32, 31, 30, 29, 28, 27, 26, 25, 2, 1, 4, 3, 5, 6, 7, 8, 14, 13, 16, 15, 10, 9, 12, 11 ]`<br>
`[ 28, 27, 26, 25, 32, 31, 30, 29, 23, 24, 21, 22, 20, 19, 18, 17, 10, 9, 12, 11, 14, 13, 16, 15, 5, 6, 7, 8, 2, 1, 4, 3 ]`<br>
`HY`<br>
`[ 3, 4, 1, 2, 7, 8, 5, 6, 11, 12, 9, 10, 15, 16, 13, 14, 19, 20, 17, 18, 23, 24, 21, 22, 27, 28, 25, 26, 31, 32, 29, 30 ]`<br>
`y^2=x^{8}-1`<br>
`CN`<br><br>


2. If the entry does not represents the full automorphism group it will have the format: 
   + group  as ordered pair [n,d] representing SmallGroup(n,d)<br>
   + signature<br>
   + conjugacy classes for this refined passport, listed as in Magma<br>
   + ordered pair representing which list of possible conjugacy classes for this group and signature the action comes from (as computed in `generate_ccnums.mag`)<br>
   + the full automorphism group as an ordered pair [n,d] representing SmallGroup(n,d)<br>
   + the signature for the full automorphism<br>
   + r lists of integers representing the r generating vectors as permutations<br><br>
For example, in genus 5 there is a family of curves with automorphism group SmallGroup(8,2) and signature [0;4,4,4,4].  This group is not the full automorphism group of the family. Instead SmallGroup(32,27) and signature [0;2,2,2,4] represent the full action, and the enty in the file g05finaldata looks like:<br><br>
` [8,2]`<br>
`[ 0, 4, 4, 4, 4 ]`<br>
`[ 5, 5, 7, 7 ]`<br>
`[ 1, 1 ]`<br>
`[32,27]`<br>
`[ 0, 2, 2, 2, 4 ]`<br>
`[ 5, 6, 7, 8, 2, 1, 4, 3 ]`<br>
`[ 5, 6, 7, 8, 2, 1, 4, 3 ]`<br>
`[ 7, 8, 5, 6, 4, 3, 2, 1 ]`<br>
`[ 7, 8, 5, 6, 4, 3, 2, 1 ]`<br>


Files Included
-----------------

* `main.mag`<br>
* `generate_ccnums.mag`<br>
* `ries.mag`    <br>
* `ries_helper_fn.mag`<br>
* `addl_data.mag` <br>
* `hyeqn.mag`<br>
* `ishypiscyc.mag` <br><br>
* `/OutputFiles/README` <br><br>
* `SupplementaryFiles/README`<br>
* `SupplementaryFiles/BreuerRaw/gxx`

Temporary Files
--------------------
In the process of running the code the following files will be created:<br>
 *	  `/SupplementaryFiles/gxx`<br>
 *	  `/OutputFiles/gxxpossible_full`<br>
 *	  `/OutputFiles/gxxfull`<br>
 *	  `/OutputFiles/gxxnotfull`<br>
 *	  `/OutputFiles/TBLDATA`<br>
 *	  `gxxfinaldata`<br>
 
See the `README` files of the respective folders for descriptions of what these files do. 


Reference
------------
More detailed explanation may be found at:
http://www.math.grinnell.edu/~paulhusj/Paulhus-lmfdb.pdf


Some of the code comes from work in the following sources:

* Breuer, Thomas. Characters and automorphism groups of compact Riemann surfaces. 
London Mathematical Society Lecture Note Series,  v. 280. Cambridge University 
Press, Cambridge, 2000.

* Ries, J. F. X. (1993). Subvarieties of moduli space determined by finite groups acting 
on surfaces. Trans. Amer. Math. Soc., 335(1):385–406.

* Shaska, Tanush. Determining the automorphism group of a hyperelliptic curve, in 
ISSAC 2003--Proceedings of the 2003 International Symposium of Symbolic and 
Algebraic Computation, pp. 248-254.

* Swinarski, David. Equations of Riemann surfaces with automorphisms (2016). 
https://arxiv.org/abs/1607.04778
