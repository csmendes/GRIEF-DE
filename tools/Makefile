CC=g++

SOURCES=$(TARGET).cpp 

OBJECTS=$(SOURCES:.cpp=.o)

EXECUTABLE=$(TARGET)

#CFLAGS := -Wall -g -O3 -Wfatal-errors -mssse3 -msse2 -march=native
CFLAGS := -ggdb 
#LDFLAGS :=  grief/grief.cpp -I   -Llib -Wl,rpath='$$ORIGIN/lib' -g `pkg-config opencv --libs`  É O CERTO
LDFLAGS :=  grief/grief.cpp -I   -Llib -Wl,-g `pkg-config opencv --libs`



# OpenCV
CFLAGS += `pkg-config opencv --cflags`

all: match_all evolve_grief annotate

match_all: match_all.cpp grief/grief.cpp 
	$(CC) match_all.cpp  $(CFLAGS) $(LDFLAGS) -o $@ 

evolve_grief: evolve_grief.cpp grief/grief.cpp 
	$(CC) evolve_grief.cpp $(CFLAGS) $(LDFLAGS) -o $@
 
evaluate: evaluate.cpp grief/grief.cpp 
	$(CC) evaluate.cpp $(CFLAGS) $(LDFLAGS) -o $@
	
annotate: annotate.cpp grief/grief.cpp 
	$(CC) annotate.cpp $(CFLAGS) $(LDFLAGS) -o $@ 

clean:
	rm -f $(OBJECTS) $(EXECUTABLE) 
	rm -f match_all evolve_grief annotate 

cleanall:
	rm -f *.o 


 