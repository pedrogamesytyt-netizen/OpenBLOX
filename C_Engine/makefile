.PHONY: all ds ds-clean pc pc-clean wii wii-clean ps2 ps2-clean

all: ds ds-clean pc pc-clean wii wii-clean

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

ps2:
	ee-gcc -O2 -I$(PS2SDK)/ee/include -I$(PS2DEV)/gsKit/include main.c -o openblox_ps2.elf -L$(PS2SDK)/ee/lib -L$(PS2DEV)/gsKit/lib -lps2sdl -lgl -lmath3d -lpacket -ldma -lgraph -ldraw -lpad -lkernel

ps2-clean:
	rm -f openblox_ps2.elf *.o
