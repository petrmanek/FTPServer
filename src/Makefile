SERVER_SOURCES=main_server.c ftp_functions.c utils.c
SERVER_OBJECTS=$(SERVER_SOURCES:.c=.o)
CC=gcc
CFLAGS=-c -Wall -std=c99 -I../include -MP -MMD
EXECUTABLE_DIRECTORY=../bin

all: ftp2_server

.c.o:
	$(CC) $(CFLAGS) $<

ftp2_server: $(SERVER_OBJECTS)
	mkdir $(EXECUTABLE_DIRECTORY)
	$(CC) -o $(EXECUTABLE_DIRECTORY)/$@ -pthread $(SERVER_OBJECTS)

clean:
	-rm $(SERVER_OBJECTS)
	-rm $(SERVER_SOURCES:.c=.d)
	-rm $(EXECUTABLE_DIRECTORY)/ftp2_server
	-rm -rf $(EXECUTABLE_DIRECTORY)
