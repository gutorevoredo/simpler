
PKGNAME=zlib
PKGVERSION=1.2.8
PKGFEXT=gz
PKGCATEGORIES=libraries
PKGDESC=Compression Library
PKGSITE=http://zlib.net/
PKGDOWN=http://zlib.net/
PKGMD5SUM=44d667c142d7cda120332623eab69f40

PKGBUILD=$(PKGPATH)/libz.so

include ../../../Makefile.in

all: $(PKGNAME).tgz

$(PKGBUILD):
	@$(MAKE) $(PKGPATH)
	@cd $(PKGPATH) && ./configure --prefix=/usr 
	@$(MAKE) -C $(PKGPATH)
	@$(STRIP) $@

$(PKGNAME).d: $(PKGBUILD)
	@$(RM) -r $@
	@mkdir -p $@/usr/lib
	@cp -a $(PKGPATH)/libz.so* $@/usr/lib
