
# reTCR

TCR Repertoire Analysis in R

## Installation

Install the development version:

``` r
devtools::install_github("Mangul-Lab-USC/reTCR")
```

## Example

``` r
library(reTCR)

proj <- reTCR::get_study(id = "PRJNA473147")

# view data
print(proj@data)
```

## 1. Basic Analysis

``` r
# summary data
print(proj@basic@summary_data)

# reads count
print(proj@basic@reads_count)

# clonotype count
print(proj@basic@clonotype_count)

# mean frequency
print(proj@basic@mean_freq)

# geometric mean of clonotype frequency
print(proj@basic@geomean_freq)

# mean length of CDR3 nucleotide sequence
print(proj@basic@mean_cdr3nt_len)

# convergence
print(proj@basic@convergence)

# spectratype
print(proj@basic@spectratype)
```

### 1.2 Statistical Analysis

D'Agostino normality test on clonotype count

``` r
library(fBasics)

fBasics::dagoTest(proj@basic@summary_data$clonotype_count)
```
Shapiro-Wilk normality test on clonotype count

``` r
library(stats)

stats::shapiro.test(proj@basic@summary_data$clonotype_count)
```