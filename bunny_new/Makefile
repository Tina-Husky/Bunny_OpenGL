CC = g++
LIBGL = -lGLEW -lglfw3 -lX11 -lXrandr -lXinerama -lXi -lXxf86vm -lXcursor -lGL -lpthread -ldl
INC = ../Include
SRC = ../src
#pattern rule
.cpp.o:
	echo rebuilding $*.o from $*.cpp
	$(CC) -I $(INC) -c $<

all: bunny calNormals

bunny: main.o $(SRC)/glad.o parser.o
	$(CC) -I $(INC) -o ./bunny $^ $(LIBGL)
	
calNormals: calNormals.o parser.o parser.h
	$(CC) -o ./calNormals $^ -I $(INC) $(LIBGL)

#main.o: main.cpp parser.h
#parser.o: parser.cpp parser.h

clean:
	rm -f *.o bunny