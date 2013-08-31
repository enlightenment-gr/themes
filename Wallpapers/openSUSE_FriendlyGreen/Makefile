# Shamelessly adapted from http://git.enlightenment.org/themes/dark.git #

EDJE_CC := edje_cc
INSTALL := install
PKG_CONFIG := pkg-config

SRCDIR := .
BUILDDIR := .
E_DESTDIR := $(shell $(PKG_CONFIG) --variable=prefix enlightenment)/share/enlightenment/data/backgrounds
E_HOMEDIR := ~/.e/e/backgrounds

THEME_NAME := openSUSE_Friendly_Green

.PHONY: all clean install install-system install-home

all: $(BUILDDIR)/$(THEME_NAME).edj

clean:
	rm -f $(BUILDDIR)/$(THEME_NAME).edj


$(BUILDDIR)/$(THEME_NAME).edj: Makefile
	$(EDJE_CC) \
		$(SRCDIR)/$(THEME_NAME).edc \
		$(BUILDDIR)/$(THEME_NAME).edj

install:
	@echo "Choose install-system or install-home"

install-system: $(BUILDDIR)/$(THEME_NAME).edj
	$(INSTALL) -D  -C -m 0644 -o root -g root \
		$(BUILDDIR)/$(THEME_NAME).edj \
		$(E_DESTDIR)/$(THEME_NAME).edj

install-home: $(BUILDDIR)/$(THEME_NAME).edj
	$(INSTALL) -D  -C -m 0644 \
		$(BUILDDIR)/$(THEME_NAME).edj \
		$(E_HOMEDIR)/$(THEME_NAME).edj
