# norm-tol-int

Exact algorithm for computing two-sided statistical tolerance intervals under a normal distribution assumption.

## Methods

The function `tolerance_factor` computes (by Gauss-Kronod quadrature)
the exact tolerance factor k for the
two-sided coverage-content and (1-alpha)-confidence tolerance interval

    TI = [Xmean - k * S, Xmean + k * S]

where Xmean = mean(X), S = std(X), X = [X_1,...,X_n] is a random sample
of size n from the distribution N(mu,sig2) with unknown mean mu and
variance sig2.

The algorithm is a Python port of the MATLAB algorithm [ToleranceFactor](https://www.mathworks.com/matlabcentral/fileexchange/24135-tolerancefactor), contributed to the MATLAB Central File Exchange
by Viktor Witkovsky. The port attempts to preserve the basic function structure of the
algorithm so comparisons back against the MATLAB code are easier to conduct.

For more details on statistical tolerance intervals the technical background on how to
compute them, see the following references:

*   Krishnamoorthy K, Mathew T. (2009). Statistical Tolerance Regions:
    Theory, Applications, and Computation. John Wiley & Sons, Inc.,
    Hoboken, New Jersey. ISBN: 978-0-470-38026-0, 512 pages.
*   Meeker, William Q.; Hahn, Gerald J.; Escobar, Luis A.. Statistical
    Intervals: A Guide for Practitioners and Researchers (Wiley Series in
    Probability and Statistics). Wiley.
*   Witkovsky V. On the exact two-sided tolerance intervals for
    univariate normal distribution and linear regression. Austrian
    Journal of Statistics 43(4), 2014, 279-92. http://
    ajs.data-analysis.at/index.php/ajs/article/viewFile/vol43-4-6/35
*   ISO 16269-6:2014: Statistical interpretation of data - Part 6:
    Determination of statistical tolerance intervals.
*   Janiga I., Garaj I.: Two-sided tolerance limits of normal
    distributions with unknown means and unknown common variability.
    MEASUREMENT SCIENCE REVIEW, Volume 3, Section 1, 2003, 75-78.

## Example

The notebook `example.ipynb` provides a very brief application example.

## Environment

The file `environment.yml` can be used to produce a `conda` environment suitable
for running the example notebook and the unit tests.

## Unit Tests

The algorithm has shown to accurately reproduce standard tables of two-sided normal tolerance
interval factors from standard sources, including the complete set of tables in
ISO 16269-6:2014 Annex F. The unit tests included here represent a sampling of that
reproduction for brevity.

To run all the unit tests, invoke the following:

    python -m unittest discover -v

## License

MIT License