# R package to access CCAP Sequence database (CCAPSeq.db)

The CCAPSeq database aims to provide a reference database annotated sequences. including SSU and LSU rRNA genes.

## Current Version

<a class="navbar-brand me-2" href="index.html">pr2database</a>
<small class="nav-text text-muted me-auto" data-bs-toggle="tooltip" data-bs-placement="bottom" title="">4.14.1</small>

## Install rCCAPSeq

```r
devtools::install_github("FDBoever/rCCAPSeq")
```

or

```r
remotes::install_github("FDBoever/rCCAPSeq")
```


## code example

```r
library(rCCAPSeq)
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



