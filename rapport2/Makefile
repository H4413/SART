LATEX=latex -shell-escape
PDF=pdflatex -shell-escape
DVIPDF=dvipdf

RM=rm -rfv
MV=mv -v
ECHO=@echo

all: pdf 

re: clean all

tex:
	${ECHO} "	*** Generating LaTeX file... ***"
	bash ./docs/gen.sh
	${ECHO} "	*** LaTeX file generated. ***"


dvi: tex 
	${ECHO} "	*** Generating dvi file... ***"
	${LATEX} *.tex
	if test -e *.toc;\
	then ${LATEX} *.tex;\
	fi
	${ECHO} "	*** dvi file generated. ***"

pdf: tex 
	${ECHO} "	*** Generating pdf file... ***"
	${PDF} *.tex
	if test -e *.toc;\
	then ${PDF} *.tex;\
	fi
	${ECHO} "	*** pdf file generated. ***"

dvipdf: dvi
	${ECHO} "	*** Generating pdf file... ***"
	${DVIPDF} *.dvi
	${ECHO} "	*** pdf file generated. ***"
	
cleanall: clean
	${RM} *.{dvi,pdf}
	${ECHO} "	*** Cleaning all done. ***"

clean:
	rm -rfv *.{tex,aux,log,toc,out,pyg}
	${ECHO} "	*** Cleaning done. ***"

