build:
	@cat reset-fonts.css core.css pageheader.css code.css cta.css projectlist.css siteheader.css > ./builds/new.css
	@java -jar ~/lib/yuicompressor/current.jar ./builds/new.css > ./builds/new.minified.css
	@cat ./copyright.css ./builds/new.minified.css > ./builds/vNew.css
	@rm -rf ./builds/new.css ./builds/new.minified.css

test:
	@find . -depth 1 -name '*.css' -exec ~/Repositories/jslint-utils/scripts/run-jslint.sh {} \;
