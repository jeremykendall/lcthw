PREFIX?=/usr/local
CFLAGS=-g -Wall -I${PREFIX}/apr/include/apr-1 -I${PREFIX}/apr/include/apr-util-1
LDFLAGS=-L${PREFIX}/apr/lib -lapr-1 -pthread -laprutil-1
OBJECTS=bstrlib.o db.o shell.o commands.o
all: devpkg

devpkg: bstrlib.o db.o shell.o commands.o
	$(CC) $(CFLAGS) devpkg.c $(OBJECTS) -o $@ $(LDFLAGS)

install: all
	install -d $(DESTDIR)/$(PREFIX)/bin/
	install devpkg $(DESTDIR)/$(PREFIX)/bin/

clean:
	rm -f *.o
	rm -f devpkg
	rm -rf *.dSYM
