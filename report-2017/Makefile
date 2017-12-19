.PHONY: run  convert pics commit

TARGET=report-pre-2017

run: $(TARGET).pdf

clean:
	latexmk -C $(TARGET).tex

convert:
	./pandoc-2.0.4/bin/pandoc -f odt -t latex --pdf-engine=lualatex book.odt -o book.tex
	./pandoc-2.0.4/bin/pandoc -s -f odt -t latex --pdf-engine=lualatex book.odt -o book.tex

$(TARGET).pdf: $(TARGET).tex
	latexmk -f $<

pics:

commit:
	gitg
	git pull origin master
	git push origin master
