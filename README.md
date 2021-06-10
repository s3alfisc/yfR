
<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- badges: start -->

[![](https://cranlogs.r-pkg.org/badges/yfR)](https://CRAN.R-project.org/yfR)

[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
<!-- badges: end -->

# Motivation

`yfR` is the second and backwards-incompatible version of
[BatchGetSymbols](https://CRAN.R-project.org/package=BatchGetSymbols), a
R package for large-scale download of financial data from Yahoo Finance.
It make it easier to fetch organized stock prices from the repository.

## Installation

    # CRAN (not yet available)
    #install.packages('yfR')

    # Github (dev version)
    devtools::install_github('msperlin/yfR')

## Main features:

-   Organizes data in a tabular/long or wide format, returning prices
    and returns (arithmetic or logarithmic)
-   A session-persistent smart cache system is available by default.
    This means that the YF data is saved locally and only missing
    portions are downloaded, if needed.
-   All dates are compared to a benchmark ticker such as SP500 and,
    whenever an individual asset does not have a sufficient number of
    dates, the software drops it from the output. This means you can
    choose to ignore tickers with high number of missing dates.
-   A customized function called `yf_convert_to_wide()` can transform
    the long table into a wide format (tickers as columns).
-   Users can choose the frequency of the resulting dataset (daily,
    weekly, monthly, yearly)
-   Parallel computing is available, speeding up the data importation
    process

## Warnings

-   Yahoo finance data is far from perfect or reliable, specially for
    individual stocks. In my experience, using it for research code with
    stock **indices** is fine and I can match it with other data
    sources. But, adjusted stock prices for **individual assets** is
    messy as stock events such as splits or dividends are not properly
    registered. I was never able to match it with other data sources,
    specially for long time periods with lots of corporate events. My
    advice is to never use the data of individual stocks in production.

-   Since version 2.6 of BatchGetSymbols, from which this package was
    based, the cache system is session-persistent by default, meaning
    that whenever you restart your R session, you lose all your cached
    data. This is a safety feature for mismatching prices due to
    corporate events.

## Example

See [vignette](https://CRAN.R-project.org/package=yfR).
