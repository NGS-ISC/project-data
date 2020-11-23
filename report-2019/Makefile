.PHONY: run  convert pics commit

YEAR=2019
TARGET=report-pre-$(2019)

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
