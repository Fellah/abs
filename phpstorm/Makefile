PWD = $(shell pwd)

build:
	docker run -it \
		-v $(PWD)/../makepkg.conf:/etc/makepkg.conf \
		-v $(PWD)/../:/srv/abs \
		-w /srv/abs/phpstorm \
		--rm abs makepkg -f -d
	scp -r $(PWD)/*.pkg.tar.xz dixet.org:/srv/html/abs
	rm -f $(PWD)/*.pkg.tar.xz

all: build

.PHONY: all build
