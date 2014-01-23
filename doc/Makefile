all: EtherAppDokumentation.tex systembeschreibung.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherAppDokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.pdf 

show: EtherAppDokumentation.tex systembeschreibung.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherAppDokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	pdflatex EtherAppDokumentation.tex 
	evince EtherAppDokumentation.pdf

clean:
	@echo "Cleaning the directory"
	rm -f *.dvi *.mt* *.aux *.log *.maf *.out *.toc *.tex~ *.log~ *.bbl *.blg

