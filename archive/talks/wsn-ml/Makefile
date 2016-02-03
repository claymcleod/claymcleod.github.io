pdf:
	@cp ./assets/styles/*.sty ./
	pandoc slides.md -t beamer --template assets/templates/beamer.template -s --latex-engine=xelatex -V theme:m --slide-level 2 -o slides.pdf
	@rm -f *.sty

revealjs:
	pandoc -t revealjs --standalone --section-divs \
		--variable theme="white" --variable transition="linear" \
		--variable revealjs-url=assets/reveal.js slides.md -o slides.html

slideous:
	pandoc -t slideous --standalone --section-divs \
		--variable theme="white" --variable transition="linear" \
	 	--slide-level 2 --variable slideous-url=assets/slideous slides.md -o slides.html
