UDEV_CFLAGS = $(shell pkg-config --cflags libudev)
UDEV_LIBS = $(shell pkg-config --libs libudev)

CC = gcc
CFLAGS = -g -Wall -O2 $(UDEV_CFLAGS)
LDFLAGS =


.PHONY: all
all: wait-for-root rzscontrol

wait-for-root: wait-for-root.o
	$(CC) $(LDFLAGS) -o $@ $< $(UDEV_LIBS)

rzscontrol: rzscontrol.o
	$(CC) $(LDFLAGS) -o $@ $<

.PHONY: clean
clean:
	rm -f wait-for-root.o wait-for-root rzscontrol.o rzscontrol core *~
