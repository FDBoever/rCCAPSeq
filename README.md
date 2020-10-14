# rCCAPSeq
R library to access CCAPSeq.db

## Install shiny

```r
devtools::install_github("FDBoever/rCCAPSeq")
```

## code example

```r
library(rCCAPSeq)
library(ggplot2)
library(dplyr)

tblSequences %>% 
	dplyr::filter(length <5000)%>% 
	select(length) %>% 
	collect() %>% 
	ggplot(aes(x= length)) +

		geom_histogram(binwidth=25,fill='firebrick') +
		scale_y_continuous(expand = c(0, 0)) +
		ylab("Number of Sequences")+
		xlab("Sequence length (nucleotides)")+
		#ggtitle('Sequence length distribution')+
		theme_bw() +
		theme(panel.border = element_blank(),
			panel.grid.major = element_blank(), 
   	     	panel.grid.minor = element_blank(),
       		axis.line = element_line(colour = "black"),
       		axis.title = element_text(size=11),
       		axis.text = element_text(size=11),
       		legend.position = "none")

```



