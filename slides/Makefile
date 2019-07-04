BUILD := \
	slides \

LATEX  := lualatex
BIBTEX := bibtex

LATEXOPTS := -interaction nonstopmode

TARGETS := $(patsubst %, %.pdf, $(BUILD))

# phony targets

all: $(TARGETS)

clean:
	rm -rf *.pdf *.aux *.bbl *.blg *.log *.nav *.out *.snm *.toc

.PHONY: all clean

# main targets

slides.pdf: slides.tex references.bib
	$(eval SRC_$@ = $(patsubst %.tex, %, $<))
	$(LATEX) $(LATEXOPTS) $(SRC_$@)
	$(BIBTEX) $(SRC_$@)
	$(LATEX) $(LATEXOPTS) $(SRC_$@)
	$(LATEX) $(LATEXOPTS) $(SRC_$@)
