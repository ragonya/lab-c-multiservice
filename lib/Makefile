.PHONY: all clean

ifeq ($(origin CC),default)
CC = gcc
endif
CFLAGS = -Wall -Wextra -O2

INCLUDE_DIR = ../include
BUILD_DIR = ../build/lib
LIBRARY = $(BUILD_DIR)/libcommon.a

OBJS = net.o http.o utils.o

all: $(LIBRARY)

$(LIBRARY): $(OBJS)
	mkdir -p $(BUILD_DIR)
	ar crs $(LIBRARY) $(OBJS)

net.o: net.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c net.c -o net.o

http.o: http.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c http.c -o http.o

utils.o: utils.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c utils.c -o utils.o

clean:
	rm -f $(OBJS)
	rm -rf ../build