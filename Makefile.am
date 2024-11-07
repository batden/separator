ACLOCAL_AMFLAGS = -I m4
MAINTAINERCLEANFILES = Makefile.in aclocal.m4 config.guess config.h.in \
		       config.sub configure depcomp install-sh ltmain.sh \
		       missing module.desktop config.rpath mkinstalldirs

SUBDIRS = src

if HAVE_PO

SUBDIRS += po

endif

EDJE_FLAGS = -v \
	     -id $(top_srcdir)/images

filesdir = $(datadir)
files_DATA = module.desktop e-module-separator.edj separator.edj

EXTRA_DIST = module.desktop.in \
	     e_modules-separator.spec.in \
	     e-module-separator.edc \
	     separator.edc \
	     images/separator.png \
	     images/module_icon.png

%.edj:  %.edc
	$(EDJE_CC) $(EDJE_FLAGS) $< $@

clean-local:
	 rm -rf separator.edj e-module-separator.edj module.desktop e_modules-separator.spec *~

uninstall:
	rm -rf $(DESTDIR)$(datadir)
