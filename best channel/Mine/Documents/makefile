name= R17_9503_Sim_Optimal_Gait_PassiveElement_Biped
SHELL=/bin/bash

all:    delx Xex delxx ok 

AllND:     Xex  gls bibt  ok 


delx:
	clear
	-rm -fr *.{out,fls,fdb_latexmk,aux,brf,bbl,idx,ilg,ind,toc,nlo,lot,lof,gls,glo,glg,ent,bls,blo,blg,xdy,tex~,bib~,log} -r

delxx:
	clear
	-rm -fr *.{out,fls,fdb_latexmk,aux,brf,bbl,idx,ilg,ind,toc,nlo,lot,lof,gls,glo,glg,ent,bls,blo,blg,xdy,tex~,bib~,log} -r
	
gls:
# 	xindy -L persian -C utf8 -I xindy -M $(name).xdy -t $(name).blg -o $(name).bls $(name).blo
	xindy -q -L english -C utf8 -I xindy -M $(name).xdy -t $(name).glg -o $(name).gls $(name).glo 
	xindy -q -L persian -C utf8 -I xindy -M $(name).xdy -t $(name).blg -o $(name).bls $(name).blo
#  	makeindex $(name)
	
Xex:
	xelatex -src-specials -interaction=nonstopmode --synctex=1 $(name).tex
	xelatex -src-specials -interaction=nonstopmode --synctex=1 $(name).tex

Xex2:
	xelatex   -synctex=1 --shell-escape  $(name).tex


bibt:
	bibtex -terse $(name).aux
	xelatex -interaction=nonstopmode --synctex=1 $(name).tex
	xelatex -interaction=nonstopmode --synctex=1 $(name).tex
# 	xelatex -interaction=batchmode -synctex=1  $(name)
# 	xelatex -interaction=batchmode -synctex=1  $(name)

ok:
	okular  --unique $(name).pdf
