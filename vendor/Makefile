#-*- mode:makefile-gmake; -*-
UNAME = $(shell uname)

all: | brews
	$(MAKE) grue
	$(MAKE) s3g
	make -C stltwalker

## Grue build
grue: Miracle-Grue/bin/miracle_grue
Miracle-Grue/bin/miracle_grue:
	cd Miracle-Grue && scons

s3g: s3g/virtualenv/bin/activate
s3g/virtualenv/bin/activate:
	cd s3g && ./setup.sh

## System
brews:
	@echo "$(UNAME)"
	ifeq ($(UNAME), Linux)
		@echo "Linux is already pre-configured."
	else
		@echo "Configuring for Mac OS X"
		@brew install avrdude || echo "AVRDude already brew installed [or failed]"
		@brew install scons || echo "scons already brew installed [or failed]"
	endif


.PHONY: all brews grue s3g
