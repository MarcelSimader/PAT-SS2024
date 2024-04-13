# Author: Marcel Simader (marcel0simader@gmail.com)
# Date: 10.05.2023
# (c) Marcel Simader 2023

# ~~~~~~~~~~~~~~~~~~~~ Edit ~~~~~~~~~~~~~~~~~~~~

TEX_NAME = PAT-Simader-Frischherz
BIB_NAME = literature.bib

# ~~~~~~~~~~~~~~~~~~~~ Maybe edit ~~~~~~~~~~~~~~~~~~~~

BIBER       = bibtex
BIBER_FLAGS =

PDFLATEX       = pdflatex
PDFLATEX_FLAGS = -interaction=nonstopmode -file-line-error

# ~~~~~~~~~~~~~~~~~~~~ Do not edit ~~~~~~~~~~~~~~~~~~~~

CONTENT_PDF := $(TEX_NAME).pdf
CONTENT_TEX := $(TEX_NAME).tex
CONTENT_BBL := $(TEX_NAME).bbl
CONTENT_BCF := $(TEX_NAME).bcf

# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~ Rules ~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.PHONY: main
main: $(CONTENT_PDF)

$(CONTENT_PDF): $(CONTENT_TEX) $(CONTENT_BBL)
	$(PDFLATEX) $(PDFLATEX_FLAGS) $(patsubst %.tex,%,$<)

$(CONTENT_BCF): $(CONTENT_TEX)
	$(PDFLATEX) $(PDFLATEX_FLAGS) $(patsubst %.tex,%,$<)

$(CONTENT_BBL): $(CONTENT_BCF) $(BIB_NAME)
	$(BIBER) $(BIBER_FLAGS) $(patsubst %.bcf,%,$<)

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

