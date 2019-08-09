# Qtlizer: comprehensive QTL annotation of GWAS results
[![Twitter](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?hashtags=Qtlizer&url=https://www.biorxiv.org/content/10.1101/495903v2&screen_name=_matmu)

This package offers the possibility to send requests to Qtlizer. Qtlizer comments on lists of common small variants and genes in humans with associated changes in gene expression using the most comprehensive database of published quantitative trait loci (QTLs) to date.

The user can use the `get_qtls()` function to make requests to Qtilzer and receives a data frame with the requested data. The queries are made with the Genehopper REST API (http://genehopper.de/rest) which can also be used directly by the user.

There is also a Qtlizer GUI that can be used (http://genehopper.de/qtlizer). More information about Qtlizer and detailed documentation about usage and available datasets can be found at  http://genehopper.de/help#qtlizer_docu .

## Installation
```R
devtools::install_github('matmu/Qtlizer')
```

## Usage
Simply call the function `get_qtls()` with your query as argument. The output will be returned as a data frame.

```R
get_qtls('rs4284742 DEFA1')
```
All kind of standard seperators (space, comma, space + comma, ...) are accepted. It is also possible to pass your query with a vector: 

```R
get_qtls(c("rs4284742", "DEFA1"))
```

Accepted query terms are variant and gene identifiers of the form: 

+ Rsid : rs + number e.g. "rs4284742"
+ reference:chr:pos e.g. "hg19:19:45412079" (Allowed references: hg19/GRCh37, hg38/GRCh38; accepted chromosomes are 1-22)
+ Gene symbol consisting of letters and numbers according to  [https://www.genenames.org/about/guidelines/]( https://www.genenames.org/about/guidelines/)


### Column meta information
The column description of the received dataframe can be accessed by calling:

```R
df = get_qtls("rs4284742")
comment(df)
```

### Try out online
If you want to try out the R package online, there is an example project on Google Colab at https://colab.research.google.com/drive/1i1sjQHCjaw2wYzVBnXQ9iaghnk-jSU95#scrollTo=5Hi6sCe7SPFb . The link leads you to the project and allows read access. To run the project, make a private copy or open the project in playground mode and sign in to Google. 


## Authors
Matthias Munz [![](https://img.shields.io/twitter/follow/_matmu?label=Follow&style=social)](https://img.shields.io/twitter/follow/_matmu?label=Follow&style=social)\
Julia Remes\
University of Lübeck, Germany


## Citation
Please cite the following article when using `Qtlizer`:

**Munz M**, Wohlers I, Simon E, Busch H, Schaefer A<sup>\*</sup> and Erdmann J <sup>\*</sup> (2018) Qtlizer: comprehensive QTL annotation of GWAS results. ***bioRxiv***

[![](https://img.shields.io/badge/doi-https%3A%2F%2Fdoi.org%2F10.1101%2F495903%20-green.svg)](https://doi.org/10.1101/495903)
[![](https://img.shields.io/badge/Altmetric-17-green.svg)](https://www.altmetric.com/details/52777590)


## License
GNU General Public License v3.0

