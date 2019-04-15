.PHONY: all clean
PDFS = main.pdf

## ================================================================
# Meta-rule for cleaning
all  : ${PDFS}
clean:
	rm -rf *.log *.aux *.out *.bbl *.blg ${PDFS} *.zip

# Build PDF from LaTeX
main.pdf : main.tex
	pdflatex $< < /dev/null
	bibtex main.aux
	pdflatex $< < /dev/null
	pdflatex $< < /dev/null

# Build PDF from SVG 
%.pdf : %.svg
	inkscape $< --export-text-to-path --export-area-drawing --export-pdf $@
