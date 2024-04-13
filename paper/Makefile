# Author: Marcel Simader (marcel0simader@gmail.com)
# Date: 10.05.2023
# (c) Marcel Simader 2023

# ~~~~~~~~~~~~~~~~~~~~ Edit ~~~~~~~~~~~~~~~~~~~~

TEX_NAME = PAT-Simader-Frischherz
BIB_NAME = literature.bib

# ~~~~~~~~~~~~~~~~~~~~ Maybe edit ~~~~~~~~~~~~~~~~~~~~

BIBTEX       = bibtex
BIBTEX_FLAGS =

PDFLATEX       = pdflatex
PDFLATEX_FLAGS = -interaction=nonstopmode -file-line-error

# ~~~~~~~~~~~~~~~~~~~~ Do not edit ~~~~~~~~~~~~~~~~~~~~

CONTENT_PDF := $(TEX_NAME).pdf
CONTENT_TEX := $(TEX_NAME).tex
CONTENT_AUX := $(TEX_NAME).aux
CONTENT_BBL := $(TEX_NAME).bbl

# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~ Rules ~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.PHONY: main
main: $(CONTENT_PDF)

$(CONTENT_PDF): $(CONTENT_TEX) $(CONTENT_BBL)
	$(PDFLATEX) $(PDFLATEX_FLAGS) $(patsubst %.tex,%,$<)

$(CONTENT_AUX): $(CONTENT_TEX)
	$(PDFLATEX) $(PDFLATEX_FLAGS) $(patsubst %.tex,%,$<)

$(CONTENT_BBL): $(CONTENT_AUX) $(BIB_NAME)
	$(BIBTEX) $(BIBTEX_FLAGS) $(patsubst %.aux,%,$<)

.PHONY: clean
clean:
	rm -f *.aux; \
	rm -f *.bbl; \
	rm -f *.bcf; \
	rm -f *.blg; \
	rm -f *.log; \
	rm -f *.xml; \
	rm -f *.out; \
	rm -f *.run
	# TODO: Comment to disable PDF cleaning
	rm -f *.pdf

