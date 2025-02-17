## Version 0.8 (2025-01-20)

### New features

* Adding "compound" distributions (ZI-Poisson, hurdle-Poisson) to QGglmm

### Bug fixes

* Fixed various typos and issues in the doc

## Version 0.7 (2018-06-15)

### Important

Due to its removal from CRAN, QGglmm dropped R2Cuba as a dependency to solve multivariate integrals. It is now using the package cubature. By taking advantage of the ["vectorised"](https://CRAN.R-project.org/package=cubature/vignettes/cubature.html) version of the algorithm, the multivariate computations of QGglmm (QGmvparams, QGvcov, QGmvmean, QGmvpsi, QGmvicc, QGmvpred) are considerably faster. Most functions are 10x-50x faster, but especially QGmvicc is 100x-500x faster. A comparison between the old and new version of the example of the man page of QGmvicc showed a decreased in computation from 25 minutes to... 4 seconds!

### New features

* Much faster computation of multivariate functions with cubature

### Bug fixes

* Fixed a bug in QGicc when var.comp == var.p
* Fixed package meta-data to avoid unsync with DESCRIPTION, e.g. for version and date

### Misc

* The source, the code in the man pages and the code in the vignette has been reformatted to follow a leaner, more consistent style of coding.

### Notes for minor versions

* Updated to 0.7.1 after complaints from CRAN checks.
* Updated to 0.7.2 to fix an issue with fancyvrb LaTeX package when building the vignette
* Updated to 0.7.3 to fix an issue with binomN and n.obs in the multivariate functions
* Updated to 0.7.4 after a problem for compiling vignette on CRAN
* Updated to 0.7.5 to remove example in QGmvicc() man page that took too long on CRAN

## Version beta 0.6 (2017-10-09)

### New features

* Mask argument for e.g. sex-based bivariate models where some predicted values do not exists in the population (i.e. individuals are either males/trait1 or females/trait2)

### Bug fixes

* Fixed some typos in the vignette
* Added dimensions checks for multivariate functions

### Misc

* Improved formatting in some parts of the code (work ongoing)
* Updated CITATION to the Genetics paper

## Version beta 0.5 (2016-09-28)

### Add a bunch of new features

* New model "ordinal" for QGparams to compute heritabilities from ordinal traits (i.e. multiple threshold)
* New functions QGicc and QGmvicc to compute Intra-Class Correlation (ICC) on the observed data scale for univariate and multivariate analyses
* New vignette "How to use QGglmm" explaining the framework, some facts about GLMMs and providing detailed examples. To access it, use `vignette("QGglmmHowTo")`.
* Adding this file: NEWS.md

## Version beta 0.4 (2016-07-13)

Multivariate code is now complete, including multivariate predictions. The univariate predictions have been changed as well: it now uses the derivative of fitness (to be calculated by the user), which allows for much improved computation time!

As usual, the code has been tested but this is still a pre-release which might contain some bugs. This version, however, is the first feature-full one, so we are switching to a beta pre-release version.

Prepared for CRAN submission. This will be the first version submitted to CRAN.

## Version alpha 0.3 (2015-08-07)

This version has an almost complete multivariate code (only the QGmvpred is missing). This multivariate code has been tested, but some glitches might still lie there.

Also added a new Gaussian model (i.e. LMM), especially useful for multivariate analysis + updated all the doc and metadata. Several other minor bug/typos fixes.

## Version alpha 0.2 (2015-07-02)

* Fix bug with mu/predict.
* More efficient width default

## Version alpha 0.1 (2015-03-26)

This is the first "alpha" development version. The package should compile and install in R and all the functions should work without any critical issue.
