# Understanding Middle Classes


[![DOI](ADD)](ADD)


Companion repository for the paper: 

 **Ecology and Class Structure: Greenhouse Gas Emissions and Social Classes in the United Kingdom**

## Data set

We use the Living Costs and Food survey 2018-2019 available from UK data service and official statistics on the GHG footprint of UK available at https://www.gov.uk/government/statistics/uks-carbon-footprint (accessed: 2022-03-01) 


## Repository structure

The repository is structured as follows:

```
.
├── data
│    └── raw
│         ├── 2018_dvhh_ukanon.sav (save LCF data to this location)
│         ├── 2018_rawhh_ukanon.sav 
│         └── ...
├── renv
└── src
```

* `data` contains preprocessed data, the subfolder `raw` contains original LCF data and GHG conversion factors. The downloaded survey data should be place here as well.
* `renv` belongs to the package of the same name and is necessary for reproducibility of our analysis
* `src` holds `.Rmd` files for reproducing our analysis, `.html` files that render code, output and results in an easily accesible format, and the `.png` plots used in the publication


If you want to familiarize yourself with the code we recommend starting by viewing the `.html` files in `src` in a web browser.

## Preliminaries: Version control

For exact reproducibility of our results we use the package manager `renv` to keep track of the versions of all packages used in a so called lockfile.

To reproduce our analysis, install `renv` then use `renv::activate()` to activate the environment specified in the lockfile. You might have to use `renv::hydrate()` to install required packages as well. Afterwards you can run the R code as you would normally do.

You can call `renv::project()` and ``renv::status()` to check whether the correct project is activated and whether it is synchronized with the lockfile.

## Preliminaries: Working directory

All scripts assume that the working directory of your R session is the root directory of this repository. If you are using Rmarkdown and knitr you might need to change the working directory in a setup cell with the command:
```
knitr::opts_knit$set(root.dir = "PATH_TO_DIR")
```
Where `PATH_TO_DIR` might either be an absolute file system path, or a path relative to your default working directory. If you are using RStudio you might also want to change your default working directory if is not set correctly.

## Prelimnaries: R version

All scripts have been tested with R version 4.1.3. If you are seeing unexpected behaviour with another R version, try switching.
