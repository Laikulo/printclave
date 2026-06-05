
all: out/py.sfs

DUMB_PYPI=dumb-pypi
MKSQUASHFS=mksquashfs

out/py.sfs: dist/packages.json
	mksquashfs dist $@ -all-root

dist/packages.json: out/whls.list
	$(DUMB_PYPI) --package-list $< --output-dir dist/ --packages-url /whls

out/whls.list: sources/*-requirements.txt
	rm dist/whls/*.whl || true
	./get-wheels
	ls -1 dist/whls > $@
	
