
ggparci
=======

Parallel Coordinates Plot with Groups medians and their Confidence Intervals

The main function `ggparci` plots parallel coordinates (gg)plot, in which each line connects the variables medians for each group.  
Confidence "bands" for the medians are added to each line. This allows the assessment of groups (clusters) separations.  
The variables can be normalized to [0,1] scale prior to plotting (see examples).  
The plot aims to facilitates the comparison of several groups across several variables, with variability assessment via the confidence intervals.  

__Note__ : This fork is an adaptation of [talgalili/ggparci](https://github.com/talgalili/ggparci) for the Medical Information Platform (MIP). The apparent changes are in the input arguments formats, package dependencies and plotting style.

## Installation

To install the latest version run:
```r
devtools::install_github('HBPMedical/ggparci')
```
## Example

Some basic examples:

``` r
library(ggparci)

ggparci(iris, groups_column = "Species")
ggparci(normalize(iris), groups_column = "Species")
ggparci(percentize(iris), groups_column = "Species")

# select only some of the variables
# plot a line for each observation
# and dont plot the CIs
ggparci(percentize(iris),columns = 1:3, groups_column = "Species", include_obs_lines = T, alpha_ci_bands = 0)

# display each group in a different facet
ggparci(data = normalize(iris), groups_column = "Species", groups_in_facets = T)

# flip the plot
ggparci(data = normalize(iris), groups_column = "Species", flip_coords = T)

```
