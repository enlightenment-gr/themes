# Shamelessly adapted from http://git.enlightenment.org/themes/dark.git #

EDJE_CC := edje_cc
INSTALL := install
PKG_CONFIG := pkg-config

SRCDIR := .
BUILDDIR := .
E_DESTDIR := $(shell $(PKG_CONFIG) --variable=prefix enlightenment)/share/enlightenment/data/backgrounds
E_HOMEDIR := ~/.e/e/backgrounds

.PHONY: all clean install install-system install-home

all: $(BUILDDIR)/ose17_pixel_perfect.edj

clean:
	rm -f $(BUILDDIR)/ose17_pixel_perfect.edj


$(BUILDDIR)/ose17_pixel_perfect.edj: Makefile
	$(EDJE_CC) \
		$(SRCDIR)/ose17_pixel_perfect.edc \
		$(BUILDDIR)/ose17_pixel_perfect.edj

install:
	@echo "Choose install-system or install-home"

install-system: $(BUILDDIR)/ose17_pixel_perfect.edj
	$(INSTALL) -D  -C -m 0644 -o root -g root \
		$(BUILDDIR)/ose17_pixel_perfect.edj \
		$(E_DESTDIR)/ose17_pixel_perfect.edj

install-home: $(BUILDDIR)/ose17_pixel_perfect.edj
	$(INSTALL) -D  -C -m 0644 \
		$(BUILDDIR)/ose17_pixel_perfect.edj \
		$(E_HOMEDIR)/ose17_pixel_perfect.edj
