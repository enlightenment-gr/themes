# Shamelessly adapted from http://git.enlightenment.org/themes/dark.git #

EDJE_CC := edje_cc
INSTALL := install
PKG_CONFIG := pkg-config

SRCDIR := .
BUILDDIR := .
E_DESTDIR := $(shell $(PKG_CONFIG) --variable=prefix enlightenment)/share/enlightenment/data/backgrounds
E_HOMEDIR := ~/.e/e/backgrounds

.PHONY: all clean install install-system install-home

all: $(BUILDDIR)/the_paper_wp.edj

clean:
	rm -f $(BUILDDIR)/the_paper_wp.edj


$(BUILDDIR)/the_paper_wp.edj: Makefile
	$(EDJE_CC) \
		$(SRCDIR)/the_paper_wp.edc \
		$(BUILDDIR)/the_paper_wp.edj

install:
	@echo "Choose install-system or install-home"

install-system: $(BUILDDIR)/the_paper_wp.edj
	$(INSTALL) -D  -C -m 0644 -o root -g root \
		$(BUILDDIR)/the_paper_wp.edj \
		$(E_DESTDIR)/the_paper_wp.edj

install-home: $(BUILDDIR)/the_paper_wp.edj
	$(INSTALL) -D  -C -m 0644 \
		$(BUILDDIR)/the_paper_wp.edj \
		$(E_HOMEDIR)/the_paper_wp.edj
