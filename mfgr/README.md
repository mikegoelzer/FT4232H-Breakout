# FTDI FT4232H Breakout Board EEPROM Programmer

Requires:  [`ftdi-eeprom`](https://github.com/nblock/libftdi/tree/master/ftdi_eeprom) utility in PATH

```
sudo apt install ftdi-eeprom
```

The EEPROM is flashed from `config.txt` file in this directory. Run `man ftdi_eeprom` to see possible config file options.

### Reading

Read the current EEPROM settings:

```
make read
```

### Flashing

Flashing from `config.txt` file's settings:

```
make flash
```

Note 1: it is not necessary to first erase the EEPROM.

Note 2: when the EEPROM is first initialized on a new board, `make flash` may need to be run **twice** for unknown reasons.

### Erasing

To erase the EEPROM (not in Makefile because not normally required):

```
sudo ftdi_eeprom --device i:0x0403:0x6011 --verbose --erase-eeprom config.txt
```

You will now need to run `make flash` **twice** to write the new settings. The first `make flash` never "takes" for some reason.
