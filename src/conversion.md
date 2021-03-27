```
pandoc recommendersysteme/01_einfuehrung.md --bibliography references.bib -csl=apa.csl --to markdown_strict -o ../recommendersysteme/01_einfuehrung.md

# maintain tex
pandoc recommendersysteme/15_relevante_objekte.md --bibliography references.bib -csl=apa.csl --to markdown_strict+raw_tex+tex_math_dollars -o ../recommendersysteme/15_relevante_objekte.md 
```