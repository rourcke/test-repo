 This is heading 1
##This is heading 2
###This is heading 3
####This is heading 4
This text is **bold**
This text is *italic*
This is text is both ***bold and italic***.
>The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continet which would one day be know as Africa, the battele for exitence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccaed land, only the small or rthe swift or the fierce could flourish, or even hope to survive.
- List item 1
- List item 2
- List item 3
- List item 1
 - List item A
 - List item B
- List item 2
1. First insturuction
1. Second instruction
1. Third instruction
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
[link text](ahmed.md)
$\sin^2 (X) + \cos^2 (x) = 1$
$$
\sin^2 (x) + \cos^2 (x) = 1
$$ {#eq:eq:sin2+cos2}

смотри формулу ([-@eq:eq:sin2+cos]).
pandoc README.md -o README.dox
FILES = $(patsubst %.md, %.docx, $(wildcard *.md)) FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
    -pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
    -pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
    @echo $(FILES)
clean:
    -rm $(FILES) *~
