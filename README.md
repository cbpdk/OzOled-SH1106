# OzOled for SH1106 (and SSD1306)

A modified version of the OzOled SSD1306 library by default configured for the SH1106. Plus the possibility to change the address, a font extended to cover to upper 128 character values, and a few extra functions.

### Configuration

By default this version has three defines in the OzOled.h file:

* For using sh1106

```
#define SH1100    //For sh1100
```
* Use extended font

```
#define EXTENDEDFONT        //Include upper half font
```

* Changeable address

```
#define CUSTOMADDRESS       //Possible to change the address, defaults to 0x3C
```

To use OzOled.h for ssd1306 without any options(except the extra functions), comment out the three defines:

```
//#define SH1100    //For sh1100
//#define EXTENDEDFONT        //Include upper half font
//#define CUSTOMADDRESS       //Possible to set address
```

If you want to set the address (CUSTOMADDRESS defined), set it like this:

```
oled.OLED_ADDRESS = 0x78;
oled.init();
```


### Extra functions

A few functions have been added. They are always availiable.

```
  //Four functions used to map scan direction and segments.
  void setScanDirectionDec();
  void setSegReMap();
  void setSegNormal();
  void setScanDirectionInc();

  //Turn display upside down
  void verticalFlip();

  //Normal display
  void verticalNormal();

  //Set position for draw_pattern()
  void set_pos(uint8_t set_col, uint8_t set_page);

  //Draw a pattern starting in current position
  void draw_pattern(uint8_t width, uint8_t pattern);

  //Draw a pattern starting in the specified position
  void draw_pattern(uint8_t set_col, uint8_t set_page, uint8_t width, uint8_t pattern);
```

## Acknowledgments

* [Oscar Liang](https://oscarliang.com/arduino-oled-display-library/) - The original Author
* [Custom address](https://github.com/mistertwo/ozoled-oled-display-096-i2c-driver-library/issues) - Original idea for optional address 
