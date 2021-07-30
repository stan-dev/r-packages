# Repository for distributing (some) stan-dev R packages

A place for publishing new versions of (some) `stan-dev` R packages before they reach CRAN and for `stan-dev` R packages and versions where releasing on CRAN is not a (current) goal. As of 2021-03-16 this is most relevant for `rstan`, where the CRAN version is unfortunately several releases behind and pushing a new version to CRAN has been difficult.

The packages currently hosted in this repository are:
 - [cmdstanr](https://github.com/stan-dev/cmdstanr)
 - [rstan](https://github.com/stan-dev/rstan)
 - [StanHeaders](https://github.com/stan-dev/stan) (required for rstan)
 - [rstanarm](https://github.com/stan-dev/rstanarm) (Survival branch - https://arxiv.org/pdf/2002.09633.pdf)

To install latest `rstan` or other packages from the repo, add `https://mc-stan.org/r-packages/` to your repository list, e.g.:

```r
install.packages("rstan", repos = c("https://mc-stan.org/r-packages/", getOption("repos")))
```

## How to publish/update packages on this repository

**For stan-dev/r-packages maintainers**

1. Install the `drat` package
```r
install.packages("drat")
```

2. Clone this repository and make sure you are on the `gh-pages` branch (the default branch).
```
git clone https://github.com/stan-dev/r-packages
git status
```

3. Create the package tarball (tar.gz) file
```r
devtools::build()
```
or

```
R CMD build packageFolder
```

4. Run `drat` to update the repository
```r
drat::insertPackage("path/to/package_tarball.tar.gz", "path/to/r-packages/")
```

For example:
```r
drat::insertPackage("cmdstanr_0.4.0.tar.gz", "r-packages/")
```

5. Commit and push changes to the `stan-dev/r-packages` repository.


**For others that wish to publish their package on https://mc-stan.org/r-packages**


1. Install the `drat` package
```r
install.packages("drat")
```

2. Fork this repository, clone your fork and make sure you are on the `gh-pages` branch (the default branch).
```
git clone https://github.com/yourusername/r-packages
git status
```

3. Create the package tarball (tar.gz) file
```r
devtools::build()
```
or

```
R CMD build packageFolder
```

4. Run `drat` to update the repository
```r
drat::insertPackage("path/to/package_tarball.tar.gz", "path/to/r-packages/")
```

For example:
```r
drat::insertPackage("cmdstanr_0.4.0.tar.gz", "r-packages/")
```

5. Commit and push changes to your repository `yourusername/r-packages`.

6. Open a pull request on this repository to add your package.
