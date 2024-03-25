# the name of the output
CO=poster
# names of files other than sources the change of which should recompile the
# source
#CHANGED_FILES_OTHER =literature.bib
CHANGED_FILES_OTHER+=$(wildcard *.tex) $(wildcard *.bib)
CHANGED_FILES_OTHER+=$(wildcard figs/*)

# List of TeX files
#TEX_FILES=$(wildcard *.tex)

###############################################################################
#                                 Rules                                       #
###############################################################################

.PHONY: all clean

all: $(CO).pdf

$(CO).pdf: $(CO).tex $(CHANGED_FILES_OTHER)
#	pdflatex -synctex=1  $(CO)
#	bibtex $(CO)
#	pdflatex $(CO)
#	pdflatex $(CO)
	rubber --unsafe --synctex --pdf $<
#	rubber-info --errors $<
#	rubber-info --check $<

zip:
	zip -r $(CO).zip figs/ literature.bib *.tex Makefile

clean:
	rm -f *.dvi *.log $(CO).blg $(CO).bbl $(CO).toc *.aux $(CO).out $(CO).lof
	rm -f $(CO).pdf
	rm -f $(CO).rubbercache
	rm -f $(CO).synctex.gz
	rm -f *~
