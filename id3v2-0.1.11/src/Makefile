CC=  g++
CFLAGS= -Wall -o 
LDLIBS= convert.cpp  genre.cpp id3v2.cpp list.cpp
CLIBS=${LDLIBS:.cpp=.o}
DESTDIR=~/Bureau/TP_solo/bin/
ID3=/home/sasl/shared/main3/env/tools
DOSSIER= field.h globals.h id3lib_frame.h id3_lib_streams.h id3lib_strings.h misc_support.h reader.h readers.h size_types.h tag.h utils.h writer.h writers.h 

all: id3v2 


%o:%cpp
	${CC} -I${ID3}/include/ -DVERSION="\"${VERSION}\"" -c -o $@ $<

id3v2:${CLIBS}
	${CC} -L${ID3}/lib ${CFLAGS} id3v2 ${CLIBS} -lid3 -lz

install: 
	mkdir -p ${DESTDIR}
	cp bin ${DESTDIR}
	nroff -man ../id3v2.1 > ${HOME}/Bureau/TP_solo/man/man1/id3v2.1

distclean:
	-rm -f id3v2 id3v2.1 

clean:
	-rm -f *.o 


.PHONY: clean

#question 8: LD_MIBRARY_PATH= `/home/sasl/shared/main3/env/tools/lib`

#question 9: Pour qu'il soit accessible de n'importe où on lui rajoute les droits en execution chmod u+x
