# R package to access CCAP Sequence database (CCAPSeq.db)

The CCAPSeq database aims to provide a reference database annotated sequences. including SSU and LSU rRNA genes.

## Current Version

![](https://img.shields.io/badge/CCAPSeq.db-v.1.3.1-brightgreen)

## Getting started

### Install rCCAPSeq

Below are two examples of how you can install the R package locally


```r
devtools::install_github("FDBoever/rCCAPSeq")
```

or

```r
remotes::install_github("FDBoever/rCCAPSeq")
```


## Usage

Load the package from within R using the following code

```r
library(rCCAPSeq)
```

### Code example

```r
library(ggplot2)
library(dplyr)

tblSequences %>% 
	dplyr::filter(length <5000)%>% 
	dplyr::select(length) %>% 
	dplyr::collect() %>% 
	ggplot2::ggplot(ggplot2::aes(x= length)) +
		ggplot2::geom_histogram(binwidth=25,fill='firebrick') +
		ggplot2::scale_y_continuous(expand = c(0, 0)) +
		ggplot2::ylab("Number of Sequences")+
		ggplot2::xlab("Sequence length (nucleotides)")+
		ggplot2::ggtitle('Sequence length distribution')+
		ggplot2::theme_bw() +
		ggplot2::theme(panel.border = element_blank(),
			panel.grid.major = element_blank(), 
   	     	panel.grid.minor = element_blank(),
       		axis.line = element_line(colour = "black"),
       		axis.title = element_text(size=11),
       		axis.text = element_text(size=11),
       		legend.position = "none")

```



