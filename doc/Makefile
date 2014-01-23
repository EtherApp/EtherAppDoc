all: EtherAppDokumentation.tex inhalt.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherAppDokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 

show: EtherAppDokumentation.tex inhalt.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherAppDokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	# Very crude fix for different PDF viewers on Linux and Mac OSX
	evince EtherAppDokumentation.pdf || TRUE
	open EtherAppDokumentation.pdf || TRUE

clean:
	@echo "Cleaning the directory"
	rm -f *.dvi *.mt* *.aux *.log *.maf *.out *.toc *.tex~ *.log~ *.bbl *.blg

