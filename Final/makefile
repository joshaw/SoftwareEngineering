PROJECT=mainfile
TEX=pdflatex
OPTIONS=-interaction nonstopmode\
		-file-line-error\
		-output-directory=$(DIR)\
		-halt-on-error
BIBTEX=bibtex -terse
DIR=build
BUILDTEX=$(TEX) $(OPTIONS) $(PROJECT).tex

CHECKDIR=mkdir -p $(DIR)

all:
	$(CHECKDIR)
	$(BUILDTEX) | egrep ":[0-9]*:" || true
#	$(BIBTEX) ${DIR}/$(PROJECT) || true
	@$(BUILDTEX) > /dev/null
	@echo -e "\n"
	@$(BUILDTEX) > /dev/null
	@xdotool search $(PROJECT).pdf key r > /dev/null 2>&1

once:
	$(BUILDTEX)

clean-all:
	find ${DIR}/ -type f -delete

clean:
	find ${DIR}/ -type f ! -name "*.pdf" -delete

# vim:ft=make
