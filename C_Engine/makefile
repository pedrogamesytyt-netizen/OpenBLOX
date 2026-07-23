.PHONY: all ds ds-clean pc pc-clean wii wii-clean ps2 ps2-clean

CC ?= ee-gcc

PS2DEV ?= /usr/local/ps2dev
PS2SDK ?= $(PS2DEV)/ps2sdk

CFLAGS = -O2 \
-I$(PS2SDK)/ee/include \
-I$(PS2DEV)/gsKit/include

LDFLAGS = \
-L$(PS2SDK)/ee/lib \
-L$(PS2DEV)/gsKit/lib \
-lps2sdl \
-lgl \
-lmath3d \
-lpacket \
-ldma \
-lgraph \
-ldraw \
-lpad \
-lkernel

SOURCES = $(wildcard *.c)
OBJECTS = $(SOURCES:.c=.o)

all:
	$(MAKE) ds
	$(MAKE) pc
	$(MAKE) wii

ds:
	$(MAKE) -C ./Makefiles -f makefile_ds

ds-clean:
	$(MAKE) -C ./Makefiles -f makefile_ds clean

pc:
	$(MAKE) -C ./Makefiles -f makefile_pc

pc-clean:
	$(MAKE) -C ./Makefiles -f makefile_pc clean

wii:
	$(MAKE) -C ./Makefiles -f makefile_rvl

wii-clean:
	$(MAKE) -C ./Makefiles -f makefile_rvl clean

ps2: $(OBJECTS)
	$(CC) $(OBJECTS) -o openblox_ps2.elf $(LDFLAGS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

ps2-clean:
	rm -f *.o openblox_ps2.elf
