all: read

read:
	sudo ftdi_eeprom --device i:0x0403:0x6011 --verbose --read-eeprom filename.bin config.txt
# filename.bin seems not to be used...

flash:
	sudo ftdi_eeprom --device i:0x0403:0x6011 --verbose --flash-eeprom config.txt
