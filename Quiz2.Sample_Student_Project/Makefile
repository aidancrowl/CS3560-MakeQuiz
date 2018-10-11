all: build doczip

build: myexe collegemain.o college.o course.o

doc: 
	doxygen config-file.conf

doczip: archive.tar

archive.tar: 
	tar cvf archive.tar .
	gzip archive.tar

myexe: collegemain.o college.o course.o
	g++ -Wall collegemain.o college.o course.o -o myexe

collegemain.o: collegemain.cc node.h
	g++ -c collegemain.cc

college.o: college.cc college.h
	g++ -c college.cc

course.o: course.cc course.h
	g++ -c course.cc 

clean:
	rm *.o myexe
	rm -r html latex
	rm *.tar.gz
