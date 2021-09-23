Homework 1
================
Philip Kim
9/22/2021

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

# Problem 1

Create a data frame comprised of:

1.  a random sample of size 10 from a standard Normal distribution
2.  a logical vector indicating whether elements of the sample are
    greater than 0
3.  a character vector of length 10
4.  a factor vector of length 10, with 3 different factor “levels”

``` r
set.seed(1)

problem1_df = 
  tibble(
  sample = rnorm(10),
  lrgr_than_0 = sample > 0,
  vec_char = c("a", "b", "c", "d", "e", "f", "g", "h", "i", "j"),
  vec_factor = factor(c("low", "medium", "high", "medium", "high", "low", "low", "medium", "high", "high"))
)
```

Try to take the mean of each variable in your dataframe. What works and
what doesn’t?

``` r
  mean(problem1_df$sample)
```

    ## [1] 0.1322028

``` r
  mean(problem1_df$lrgr_than_0)
```

    ## [1] 0.6

``` r
  mean(problem1_df$vec_char)
```

    ## Warning in mean.default(problem1_df$vec_char): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
  mean(problem1_df$vec_factor)
```

    ## Warning in mean.default(problem1_df$vec_factor): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

After calculating the means of all four variables in the data frame, the
mean was calculated for the random sample and the logical vector.
However, it did not work for the character vector or the factor vector.
It displayed that the “argument is not numeric or logical: returning
NA”.
