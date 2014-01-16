all: EtherApp_Dokumentation.tex einordnung.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherApp_Dokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherApp_Dokumentation.tex 
	pdflatex EtherApp_Dokumentation.tex 
	pdflatex EtherApp_Dokumentation.pdf 

show: EtherApp_Dokumentation.tex einordnung.tex abk.tex quellen.bib literatur.bib deckblatt.tex
	@echo "Creating the pdf file."
	pdflatex EtherApp_Dokumentation.tex 
	bibtex que.aux
	bibtex lit.aux
	pdflatex EtherApp_Dokumentation.tex 
	pdflatex EtherApp_Dokumentation.tex 
	pdflatex EtherApp_Dokumentation.tex 
	evince EtherApp_Dokumentation.pdf

clean:
	@echo "Cleaning the directory"
	rm -f *.dvi *.mt* *.aux *.log *.maf *.out *.toc *.tex~ *.log~ *.bbl *.blg

