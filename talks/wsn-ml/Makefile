pdf:
	@cp ./assets/styles/*.sty ./
	pandoc slides.md -t beamer --template assets/templates/beamer.template -s --latex-engine=xelatex -V theme:m --slide-level 2 -o slides.pdf
	@rm -f *.sty

revealjs:
	pandoc -t revealjs --standalone --section-divs \
		--variable theme="white" --variable transition="linear" \
		--slide-level 2 --variable revealjs-url=assets/reveal.js slides.md -o slides.html
