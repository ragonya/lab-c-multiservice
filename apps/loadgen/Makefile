.PHONY: all clean

ifeq ($(origin CC),default)
CC = gcc
endif
CFLAGS ?= -Wall -Wextra -O2

INCLUDE_DIR = ../../include
LIB_DIR = ../../build/lib

TARGET = loadgen
OBJS = main.o stats.o

all: $(TARGET)

$(TARGET): $(OBJS) $(LIB_DIR)/libcommon.a
	$(CC) $(CFLAGS) $(OBJS) -L$(LIB_DIR) -lcommon -o $(TARGET)

main.o: main.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c main.c -o main.o

stats.o: stats.c
	$(CC) $(CFLAGS) -I$(INCLUDE_DIR) -c stats.c -o stats.o

clean:
	rm -f $(OBJS) $(TARGET)