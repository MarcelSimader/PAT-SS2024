# Author: Marcel Simader (marcel0simader@gmail.com)
# Date: 04.11.2023
# License: See 'LICENSE'.

# ~~~~~~~~~~~~~~~~~~~~ Edit ~~~~~~~~~~~~~~~~~~~~

CONTENT    = content
PACKAGES   = packages
LITERATURE = literature

BIBER       = biber
BIBER_FLAGS =

LC       = xelatex
LC_FLAGS = -interaction=nonstopmode -file-line-error

# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~ Rules ~~~~~~~~~~~~~~~~~~~~
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.PHONY: all
all: $(CONTENT).pdf

$(CONTENT).bcf: $(CONTENT).tex $(PACKAGES).tex
	$(LC) $(LC_FLAGS) $(CONTENT).tex

$(CONTENT).bbl: $(CONTENT).bcf $(LITERATURE).bib
	$(BIBER) $(BIBER_FLAGS) $(CONTENT).bcf

$(CONTENT).pdf: $(CONTENT).tex $(PACKAGES).tex $(CONTENT).bbl
	$(LC) $(LC_FLAGS) $(CONTENT).tex

.PHONY: clean
clean:
	rm -f *.aux; \
	rm -f *.bbl; \
	rm -f *.bcf; \
	rm -f *.blg; \
	rm -f *.log; \
	rm -f *.xml; \
	rm -f *.out; \
	rm -f *.run; \
	rm -f *.nav; \
	rm -f *.snm; \
	rm -f *.toc; \
	rm -f *.glo; \
	rm -f *.ist
	# TODO: Comment to disable PDF cleaning
	# rm -f *.pdf

