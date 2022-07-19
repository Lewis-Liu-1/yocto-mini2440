#!/usr/bin/make
LDFLAGS=-lusb
CC =gcc
all: s3c2410_boot_usb

clean:
	-rm -f *.o s3c2410_boot_usb

s3c2410_boot_usb: boot_usb.o
	$(CC) -o $@ $< $(LDFLAGS)

boot_usb.o: boot_usb.c
	$(CC) $(CFLAGS) -o $@ -c $<

.PHONY: all clean
