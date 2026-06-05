
all: git.sfs

.PHONY: repos all

repos:
	./clone-repos

git.sfs: repos
	mksquashfs repos $@ -all-root

