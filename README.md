# Repository for distributing (some) stan-dev R packages

A place for publishing new versions of (some) `stan-dev` R packages before they reach CRAN and for `stan-dev` R packages and versions where releasing on CRAN is not a (current) goal.

**Instructions for publishing or updating on this repository**

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
drat::insertPackage("posterior_0.0.3.tar.gz", "r-packages/")
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
drat::insertPackage("posterior_0.0.3.tar.gz", "r-packages/")
```

5. Commit and push changes to your repository `yourusername/r-packages`.

6. Open a pull request on this repository to add your package.


