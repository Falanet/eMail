# Dlib makefile
MAKE = make
VERSION = @ver@
SRCDIR = src/
DESTDIR = 
CC = gcc
CFLAGS = -g -O2 -Wall -W -I/home/machaddr/Labs/Falanet/dlib -I/home/machaddr/Labs/Falanet/dlib/src -I/home/machaddr/Labs/Falanet/dlib/include -I../include  -DHAVE_CONFIG_H
LDFLAGS = 
LIBS = -lnsl -lm 

prefix = /usr/local
exec_prefix = ${prefix}
bindir = ${exec_prefix}/bin
sbindir = ${exec_prefix}/sbin
libdir = ${exec_prefix}/lib
includedir = ${prefix}/include
mandir = ${datarootdir}/man
docdir = ${datarootdir}/doc/${PACKAGE_TARNAME}
sysconfdir = ${prefix}/etc
datarootdir = ${prefix}/share

bin_suffix = 

FILES = src/dnet.o src/dhash.o src/dlist.o src/dstrbuf.o src/dutil.o src/dvector.o

.PHONY: all clean-all clean distclean install uninstall

.c.o:
	$(CC) $(CFLAGS) -c $*.c -o $*.o

all: $(FILES)
	ar rc libdlib.a $(FILES)

test:
	$(CC) $(CFLAGS) -o test test.c libdlib.a -lm

dlisttest:
	$(CC) $(CFLAGS) -o dlisttest dlisttest.c libdlib.a -lm

dhashtest:
	$(CC) $(CFLAGS) -o dhashtest dhashtest.c libdlib.a -lm

install:
	mkdir -p $(DESTDIR)/$(libdir)/
	mkdir -p $(DESTDIR)/$(includedir)/dlib/
	install -m0644 libdlib.a $(DESTDIR)/$(libdir)/
	install -m0644 include/* $(DESTDIR)/$(includedir)/dlib/

clean:
	rm -f src/*.o *.so *.a test

