## ESP_AT_Lib

[![arduino-library-badge](https://www.ardu-badge.com/badge/ESP_AT_Lib.svg?)](https://www.ardu-badge.com/ESP_AT_Lib)
[![GitHub release](https://img.shields.io/github/release/khoih-prog/ESP_AT_Lib.svg)](https://github.com/khoih-prog/ESP_AT_Lib/releases)
[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/LICENSE)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](#Contributing)
[![GitHub issues](https://img.shields.io/github/issues/khoih-prog/ESP_AT_Lib.svg)](http://github.com/khoih-prog/ESP_AT_Lib/issues)

---
---

This is an ESP8266/ESP32 wrapper library for Arduino providing an easy-to-use way to manipulate ESP8266/ESP32-AT shields.

This library is based on, modified and improved from [ITEADLIB_Arduino_WeeESP8266](https://github.com/itead/ITEADLIB_Arduino_WeeESP8266)

---

### Releases v1.0.0

1. Add support to **nRF52 (AdaFruit Feather nRF52832, nRF52840 Express, BlueFruit Sense, Itsy-Bitsy nRF52840 Express, Metro nRF52840 Express, NINA_B302_ublox, NINA_B112_ublox, etc.)**.
2. Add support to **Adafruit SAMD21/SAM51 (Itsy-Bitsy M0/M4, Metro M0/M4, Grand Central M4, Feather M0/M4 Express, etc.)**.
3. Add support to **STM32F/L/H/G/WB/MP1, Teensy, SAM DUE**.
4. Add support to **ESP32-AT** shields.
5. Add debug AT command output

---

### Prerequisites

 1. [`Arduino IDE 1.8.13+` for Arduino](https://www.arduino.cc/en/Main/Software)
 2. [`Arduino AVR core 1.8.3+`](https://github.com/arduino/ArduinoCore-avr) for Arduino AVR boards. Use Arduino Board Manager to install.
 3. [`Arduino Core for STM32 v1.9.0+`](https://github.com/khoih-prog/Arduino_Core_STM32) for STM32 boards (Nucleo-144 NUCLEO_F767ZI, Nucleo-64 NUCLEO_L053R8, etc.)
 4. [`Teensy core 1.53+`](https://www.pjrc.com/teensy/td_download.html) for Teensy (4.1, 4.0, 3.6, 3.5, 3,2, 3.1, 3.0, LC) boards
 5. [`Arduino SAM DUE core 1.6.12+`](https://www.arduino.cc/en/Guide/ArduinoDue) for SAM DUE ARM Cortex-M3 boards
 6. [`Arduino SAMD core 1.8.10+`](https://www.arduino.cc/en/Guide/ArduinoM0) for SAMD ARM Cortex-M0+ boards  (Nano 33 IoT, etc.).
 7. [`Adafruit SAMD core 1.6.4+`](https://www.adafruit.com/)  for SAMD ARM Cortex-M0+ and M4 boards (Itsy-Bitsy M4, etc.)
 8. [`Seeeduino SAMD core 1.8.1+`](https://www.seeedstudio.com/) for SAMD21/SAMD51 boards (XIAO M0, Wio Terminal, etc.) 
 9. [`Adafruit nRF52 v0.21.0+`](www.adafruit.com) for nRF52 boards such as AdaFruit Feather nRF52840 Express, NINA_B302_ublox, NINA_B112_ublox, etc.
10. [`Ai-Thinker AT Firmware v1.5.4`](AT_Firmwares/At_firmware_bin1.54.zip) or [`AT Firmware v1.7.4.0`](AT_Firmwares/AT_Firmware_bin_1.7.4.0.zip) for ESP8266-AT shields.
11. [`AT version_2.1.0.0_dev`](AT_Firmwares/AT_version_2.1.0.0_dev.zip) for ESP32-AT shields.
12. `AT version_1.1.4` for WIS600-01S and W600-AT WiFi shields.

---

### Important Notes about AT Firmwares

1. Tested OK with for ESP8266-AT shields:
  - [`Ai-Thinker AT Firmware v1.5.4`](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/AT_Firmwares/At_firmware_bin1.54.zip)
  
    ```
    AT version:1.1.0.0(May 11 2016 18:09:56)
    SDK version:1.5.4(baaeaebb)
    Ai-Thinker Technology Co. Ltd.
    Jun 13 2016 11:29:20
    ```
  - [`AT Firmware v1.7.4.0`](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/AT_Firmwares/AT_Firmware_bin_1.7.4.0.zip)
  
    ```
    AT version:1.7.4.0(May 11 2020 19:13:04)
    SDK version:3.0.4(9532ceb)
    compile time:May 27 2020 10:12:17
    Bin version(Wroom 02):1.7.4
    ```
    
  - [`WIS600-01S`](https://www.aliexpress.com/item/32956707239.html) and [`W600`](https://www.seeedstudio.com/w600.html) using either ESP8266 or ESP32-AT commands and stock firmware
  
    ```
    AT version:1.1.4(Dec 05 2018 11:06:45)
    SDK version:3.0.0
    Dec 05 2018 11:06:45
    ```
  
  
2. Tested OK with for ESP32-AT shields:
  - [`AT version_2.1.0.0_dev`](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/AT_Firmwares/AT_version_2.1.0.0_dev.zip)
    
    ```
    AT version:2.1.0.0-dev(4f6b92c - Jun 10 2020 10:36:54)
    SDK version:v4.0.1-193-ge7ac221b4
    compile time(b85a8df):Jun 18 2020 14:00:59
    Bin version:2.0.0(WROOM-32)
    ```
    
    See instructions at [AT Command Core](https://github.com/espressif/esp-at) and [ESP_AT_Get_Started](https://github.com/espressif/esp-at/blob/master/docs/en/get-started/ESP_AT_Get_Started.md)
  
3. Upload [`AT Firmware v1.7.4.0`](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/AT_Firmwares/AT_Firmware_bin_1.7.4.0.zip) bin files to correct locations as follows:

```
# BOOT MODE

### Flash size 8Mbit: 512KB+512KB
    boot_v1.2+.bin              0x00000
    user1.1024.new.2.bin        0x01000
    esp_init_data_default.bin   0xfc000
    blank.bin                   0x7e000 & 0xfe000


### Flash size 16Mbit-C1: 1024KB+1024KB
    boot_v1.2+.bin              0x00000
    user1.2048.new.5.bin        0x01000
    esp_init_data_default.bin   0x1fc000
    blank.bin                   0xfe000 & 0x1fe000
```

4. Test before using different AT-Firmware Version at your own risks. Just use any simple example to verify if the AT-firmware is OK.
5. Compatible AT-Firmare version will be updated. Check for all supported AT Firmwares and download them from [AT_Firmwares](https://github.com/khoih-prog/ESP_AT_Lib/tree/master/AT_Firmwares).
6. Support to ESP32-AT-command shields has been added to permit using new library [ESP_AT_Lib](https://github.com/khoih-prog/ESP_AT_Lib) to replace [Blynk's BlynkESP8266_Lib](https://github.com/blynkkk/blynk-library/releases/Blynk_Release_v0.6.1.zip). The same [ESP_AT_Lib](https://github.com/khoih-prog/ESP_AT_Lib) can also be use for ESP8266-AT shields.


---

## Installation

### Use Arduino Library Manager
The best and easiest way is to use `Arduino Library Manager`. Search for `ESP_AT_Lib`, then select / install the latest version.
You can also use this link [![arduino-library-badge](https://www.ardu-badge.com/badge/ESP_AT_Lib.svg?)](https://www.ardu-badge.com/ESP_AT_Lib) for more detailed instructions.

### Manual Install

Another way to install is to:

1. Navigate to [ESP_AT_Lib](https://github.com/khoih-prog/ESP_AT_Lib) page.
2. Download the latest release `ESP_AT_Lib-master.zip`.
3. Extract the zip file to `ESP_AT_Lib-master` directory 
4. Copy whole `ESP_AT_Lib-master/src` folder to Arduino libraries' directory such as `~/Arduino/libraries/`.

### VS Code & PlatformIO:

1. Install [VS Code](https://code.visualstudio.com/)
2. Install [PlatformIO](https://platformio.org/platformio-ide)
3. Install [**ESP_AT_Lib** library](https://platformio.org/lib/show/7511/ESP_AT_Lib) by using [Library Manager](https://platformio.org/lib/show/7511/ESP_AT_Lib/installation). Search for **ESP_AT_Lib** in [Platform.io Author's Libraries](https://platformio.org/lib/search?query=author:%22Khoi%20Hoang%22)
4. Use included [platformio.ini](platformio/platformio.ini) file from examples to ensure that all dependent libraries will installed automatically. Please visit documentation for the other options and examples at [Project Configuration File](https://docs.platformio.org/page/projectconf.html)

---
---

### Packages' Patches

 1. **To be able to compile, run and automatically detect and display BOARD_NAME on nRF52840/nRF52832 boards**, you have to copy the whole [nRF52 0.21.0](Packages_Patches/adafruit/hardware/nrf52/0.21.0) directory into Adafruit nRF52 directory (~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0). 

Supposing the Adafruit nRF52 version is 0.21.0. These files must be copied into the directory:
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/platform.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/boards.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B302_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B302_ublox/variant.cpp`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B112_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/variants/NINA_B112_ublox/variant.cpp`
- **`~/.arduino15/packages/adafruit/hardware/nrf52/0.21.0/cores/nRF5/Udp.h`**

Whenever a new version is installed, remember to copy these files into the new version directory. For example, new version is x.yy.z
These files must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/platform.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/boards.txt`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B302_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B302_ublox/variant.cpp`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B112_ublox/variant.h`
- `~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/variants/NINA_B112_ublox/variant.cpp`
- **`~/.arduino15/packages/adafruit/hardware/nrf52/x.yy.z/cores/nRF5/Udp.h`**

 2. **To be able to compile and run on Teensy boards**, you have to copy the file [Teensy boards.txt](Packages_Patches/hardware/teensy/avr/boards.txt) into Teensy hardware directory (./arduino-1.8.12/hardware/teensy/avr/boards.txt). 

Supposing the Arduino version is 1.8.12. This file must be copied into the directory:

- `./arduino-1.8.12/hardware/teensy/avr/boards.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `./arduino-x.yy.zz/hardware/teensy/avr/boards.txt`

 3. **To be able to compile and run on SAM DUE boards**, you have to copy the whole [SAM DUE](Packages_Patches/arduino/hardware/sam/1.6.12) directory into Arduino sam directory (~/.arduino15/packages/arduino/hardware/sam/1.6.12). 

Supposing the Arduino SAM core version is 1.6.12. This file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/sam/1.6.12/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/sam/x.yy.zz/platform.txt`

 4. ***To be able to compile without error and automatically detect and display BOARD_NAME on Arduino SAMD (Nano-33-IoT, etc) boards***, you have to copy the whole [Arduino SAMD cores 1.8.10](Packages_Patches/arduino/hardware/samd/1.8.10) directory into Arduino SAMD directory (~/.arduino15/packages/arduino/hardware/samd/1.8.10).
 
#### For core version v1.8.10+

Supposing the Arduino SAMD version is 1.8.10. Now only one file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/samd/1.8.10/platform.txt`

Whenever a new version is installed, remember to copy this files into the new version directory. For example, new version is x.yy.zz

This file must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/samd/x.yy.zz/platform.txt`
 
#### For core version v1.8.9-

Supposing the Arduino SAMD version is 1.8.9. These files must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/samd/1.8.9/platform.txt`
- ***`~/.arduino15/packages/arduino/hardware/samd/1.8.9/cores/arduino/Arduino.h`***

Whenever a new version is installed, remember to copy these files into the new version directory. For example, new version is x.yy.z

These files must be copied into the directory:

- `~/.arduino15/packages/arduino/hardware/samd/x.yy.z/platform.txt`
- ***`~/.arduino15/packages/arduino/hardware/samd/x.yy.z/cores/arduino/Arduino.h`***
 
 This is mandatory to fix the ***notorious Arduino SAMD compiler error***. See [Improve Arduino compatibility with the STL (min and max macro)](https://github.com/arduino/ArduinoCore-samd/pull/399)
 
```
 ...\arm-none-eabi\include\c++\7.2.1\bits\stl_algobase.h:243:56: error: macro "min" passed 3 arguments, but takes just 2
     min(const _Tp& __a, const _Tp& __b, _Compare __comp)
```

Whenever the above-mentioned compiler error issue is fixed with the new Arduino SAMD release, you don't need to copy the `Arduino.h` file anymore.

 5. **To be able to automatically detect and display BOARD_NAME on Adafruit SAMD (Itsy-Bitsy M4, etc) boards**, you have to copy the file [Adafruit SAMD platform.txt](Packages_Patches/adafruit/hardware/samd/1.6.4) into Adafruit samd directory (~/.arduino15/packages/adafruit/hardware/samd/1.6.4). 

Supposing the Adafruit SAMD core version is 1.6.4. This file must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/samd/1.6.4/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/adafruit/hardware/samd/x.yy.zz/platform.txt`

 6. **To be able to automatically detect and display BOARD_NAME on Seeeduino SAMD (XIAO M0, Wio Terminal, etc) boards**, you have to copy the file [Seeeduino SAMD platform.txt](Packages_Patches/Seeeduino/hardware/samd/1.8.1) into Adafruit samd directory (~/.arduino15/packages/Seeeduino/hardware/samd/1.8.1). 

Supposing the Seeeduino SAMD core version is 1.8.1. This file must be copied into the directory:

- `~/.arduino15/packages/Seeeduino/hardware/samd/1.8.1/platform.txt`

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz
This file must be copied into the directory:

- `~/.arduino15/packages/Seeeduino/hardware/samd/x.yy.zz/platform.txt`

7. **To use Serial1 on some STM32 boards without Serial1 definition (Nucleo-144 NUCLEO_F767ZI, Nucleo-64 NUCLEO_L053R8, etc.) boards**, you have to copy the files [STM32 variant.h](Packages_Patches/STM32/hardware/stm32/1.9.0) into STM32 stm32 directory (~/.arduino15/packages/STM32/hardware/stm32/1.9.0). You have to modify the files corresponding to your boards, this is just an illustration how to do.

Supposing the STM32 stm32 core version is 1.9.0. These files must be copied into the directory:

- `~/.arduino15/packages/STM32/hardware/stm32/1.9.0/variants/NUCLEO_F767ZI/variant.h` for Nucleo-144 NUCLEO_F767ZI.
- `~/.arduino15/packages/STM32/hardware/stm32/1.9.0/variants/NUCLEO_L053R8/variant.h` for Nucleo-64 NUCLEO_L053R8.

Whenever a new version is installed, remember to copy this file into the new version directory. For example, new version is x.yy.zz,
theses files must be copied into the corresponding directory:

- `~/.arduino15/packages/STM32/hardware/stm32/x.yy.zz/variants/NUCLEO_F767ZI/variant.h`
- `~/.arduino15/packages/STM32/hardware/stm32/x.yy.zz/variants/NUCLEO_L053R8/variant.h`


---

### HOWTO Get started

On the home page of API documentation, the tabs of Examples, Classes and Modules 
will be useful for Arduino lovers. 

### API List

```cpp

    bool 	kick (void) : Verify ESP8266 whether live or not.
     
    bool 	restart (void) : Restart ESP8266 by "AT+RST".
     
    String 	getVersion (void) : Get the version of AT Command Set.
     
    bool 	setOprToStation (void) : Set operation mode to staion.
     
    bool 	setOprToSoftAP (void) : Set operation mode to softap.
     
    bool 	setOprToStationSoftAP (void) : Set operation mode to station + softap.
    
    uint8_t  getOprMode(void) : Get the operation mode.
     
    String 	getAPList (void) : Search available AP list and return it.
     
    bool 	joinAP (String ssid, String pwd) : Join in AP. 
     
    bool 	leaveAP (void) : Leave AP joined before. 
     
    bool 	setSoftAPParam (String ssid, String pwd, uint8_t chl=7, uint8_t ecn=4) : Set SoftAP parameters. 
     
    String 	getJoinedDeviceIP (void) : Get the IP list of devices connected to SoftAP. 
     
    String 	getIPStatus (void) : Get the current status of connection(UDP and TCP). 
     
    String 	getLocalIP (void) : Get the IP address of ESP8266. 
     
    bool 	enableMUX (void) : Enable IP MUX(multiple connection mode). 
     
    bool 	disableMUX (void) : Disable IP MUX(single connection mode). 
     
    bool 	createTCP (String addr, uint32_t port) : Create TCP connection in single mode. 
     
    bool 	releaseTCP (void) : Release TCP connection in single mode. 
     
    bool 	registerUDP (String addr, uint32_t port) : Register UDP port number in single mode. 
     
    bool 	unregisterUDP (void) : Unregister UDP port number in single mode. 
     
    bool 	createTCP (uint8_t mux_id, String addr, uint32_t port) : Create TCP connection in multiple mode. 
     
    bool 	releaseTCP (uint8_t mux_id) : Release TCP connection in multiple mode. 
     
    bool 	registerUDP (uint8_t mux_id, String addr, uint32_t port) : Register UDP port number in multiple mode. 
     
    bool 	unregisterUDP (uint8_t mux_id) : Unregister UDP port number in multiple mode. 
     
    bool 	setTCPServerTimeout (uint32_t timeout=180) : Set the timeout of TCP Server. 
    
    bool 	startServer (uint32_t port=333) ： Start Server(Only in multiple mode).

    bool 	stopServer (void) : Stop Server(Only in multiple mode).
 
    bool 	startTCPServer (uint32_t port=333) : Start TCP Server(Only in multiple mode). 
     
    bool 	stopTCPServer (void) : Stop TCP Server(Only in multiple mode). 
     
    bool 	send (const uint8_t *buffer, uint32_t len) : Send data based on TCP or UDP builded already in single mode. 
     
    bool 	send (uint8_t mux_id, const uint8_t *buffer, uint32_t len) : Send data based on one of TCP or UDP builded already in multiple mode. 

    bool 	sendFromFlash (const uint8_t *buffer, uint32_t len) : Send data based on TCP or UDP builded already in single mode. 
     
    bool 	sendFromFlash (uint8_t mux_id, const uint8_t *buffer, uint32_t len) : Send data based on one of TCP or UDP builded already in multiple mode. 
     
    uint32_t 	recv (uint8_t *buffer, uint32_t buffer_size, uint32_t timeout=1000) : Receive data from TCP or UDP builded already in single mode. 
     
    uint32_t 	recv (uint8_t mux_id, uint8_t *buffer, uint32_t buffer_size, uint32_t timeout=1000) : Receive data from one of TCP or UDP builded already in multiple mode. 
     
    uint32_t 	recv (uint8_t *coming_mux_id, uint8_t *buffer, uint32_t buffer_size, uint32_t timeout=1000) : Receive data from all of TCP or UDP builded already in multiple mode. 
```
---

### Suppported Boards
  
  - Arduino MEGA
  - SAM DUE
  - **Arduino SAMD21 (ZERO, MKR, NANO_33_IOT, M0, M0 Pro, AdaFruit CIRCUITPLAYGROUND_EXPRESS, etc.)**
  - **Adafruit SAMD21/SAM51 (Itsy-Bitsy M0/M4, Metro M0/M4, Grand Central M4, Feather M0/M4 Express, etc.)**
  - Teensy
  - **nRF52 (AdaFruit Feather nRF52832, nRF52840 Express, BlueFruit Sense, Itsy-Bitsy nRF52840 Express, Metro nRF52840 Express, NINA_B302_ublox, NINA_B112_ublox, etc.)**
  - **STM32F (STM32F1, F2, F3, F4, F7, etc.)**


### Hardware Connection

ESP_AT_Lib library only needs an UART for hardware connection. All communications are done via UART. In each example, you must specify the UART used by mainboard to communicate with ESP8266/ESP32-AT firmware.

#### MEGA, SAM DUE

For MEGA and SAM DUE, `Serial1` or `Serial3` will be used if you create an object (named wifi)  of class ESP8266 in your code like this:

    #include "ESP_AT_Lib.h"
    ESP8266 wifi(&Serial1);

The connection should be like these:

    ESP8266_TX->RX1(D19)
    ESP8266_RX->TX1(D18)
    ESP8266_CH_PD->3.3V
    ESP8266_VCC->3.3V
    ESP8266_GND->GND

---

### Attention

The size of data from ESP8266/ESP32-AT is sometimes too big for Arduino boards, so the library can't receive the whole buffer because the size of the hardware serial buffer, defined in HardwareSerial.h, is too small.

The `SERIAL_TX_BUFFER_SIZE` and `SERIAL_RX_BUFFER_SIZE` are already redefined to 256 for Mega, and 2048 for other boards

```cpp
#if ( defined(ARDUINO_AVR_ADK) || defined(ARDUINO_AVR_MEGA) || defined(ARDUINO_AVR_MEGA2560) )
  #if defined(SERIAL_TX_BUFFER_SIZE)
    #undef SERIAL_TX_BUFFER_SIZE
    #define SERIAL_TX_BUFFER_SIZE     256
  #endif
  
  #if defined(SERIAL_RX_BUFFER_SIZE)
    #undef SERIAL_RX_BUFFER_SIZE
    #define SERIAL_RX_BUFFER_SIZE     256
  #endif
#else
#if defined(SERIAL_TX_BUFFER_SIZE)
    #undef SERIAL_TX_BUFFER_SIZE
    #define SERIAL_TX_BUFFER_SIZE     2048
  #endif
  
  #if defined(SERIAL_RX_BUFFER_SIZE)
    #undef SERIAL_RX_BUFFER_SIZE
    #define SERIAL_RX_BUFFER_SIZE     2048
  #endif
#endif
```
---
---

### Examples 

1. [ConnectWiFi](examples/ConnectWiFi)
2. [HTTPGET](examples/HTTPGET)
3. [TCPClientSingle](examples/TCPClientSingle)
4. [TCPClientMultiple](examples/TCPClientMultiple)
5. [TCPServer](examples/TCPServer)
6. [UDPClientSingle](examples/UDPClientSingle)
7. [UDPClientMultiple](examples/UDPClientMultiple)

---

#### Example [TCPServer](examples/TCPServer)

Please take a look at other examples, as well.


```cpp
/* Comment this out to disable prints and save space */
#define ESP_AT_DEBUG_OUTPUT     Serial

#define _ESP_AT_LOGLEVEL_       4

// Uncomment to use ESP32-AT commands
//#define USE_ESP32_AT      true

#if ( defined(NRF52840_FEATHER) || defined(NRF52832_FEATHER) || defined(NRF52_SERIES) || defined(ARDUINO_NRF52_ADAFRUIT) || \
      defined(NRF52840_FEATHER_SENSE) || defined(NRF52840_ITSYBITSY) || defined(NRF52840_CIRCUITPLAY) || defined(NRF52840_CLUE) || \
      defined(NRF52840_METRO) || defined(NRF52840_PCA10056) || defined(PARTICLE_XENON) || defined(NINA_B302_ublox) || defined(NINA_B112_ublox) )
#if defined(ESP_AT_USE_NRF528XX)
#undef ESP_AT_USE_NRF528XX
#endif
#define ESP_AT_USE_NRF528XX      true
#endif

#if ( defined(ARDUINO_SAMD_ZERO) || defined(ARDUINO_SAMD_MKR1000) || defined(ARDUINO_SAMD_MKRWIFI1010) \
   || defined(ARDUINO_SAMD_NANO_33_IOT) || defined(ARDUINO_SAMD_MKRFox1200) || defined(ARDUINO_SAMD_MKRWAN1300) \
   || defined(ARDUINO_SAMD_MKRWAN1310) || defined(ARDUINO_SAMD_MKRGSM1400) || defined(ARDUINO_SAMD_MKRNB1500) \
   || defined(ARDUINO_SAMD_MKRVIDOR4000) || defined(__SAMD21G18A__) || defined(ARDUINO_SAMD_CIRCUITPLAYGROUND_EXPRESS) \
   || defined(__SAMD51__) || defined(__SAMD51J20A__) || defined(__SAMD51J19A__) || defined(__SAMD51G19A__) )
#if defined(ESP_AT_USE_SAMD)
#undef ESP_AT_USE_SAMD
#endif
#define ESP_AT_USE_SAMD           true
#endif

#if ( defined(ARDUINO_AVR_ADK) || defined(ARDUINO_AVR_MEGA) || defined(ARDUINO_AVR_MEGA2560) )
#if defined(ESP_AT_USE_AVR)
#undef ESP_AT_USE_AVR
#endif
#define ESP_AT_USE_AVR      true
#endif

#if ( defined(ARDUINO_SAM_DUE) || defined(__SAM3X8E__) )
#if defined(ESP_AT_USE_SAM_DUE)
#undef ESP_AT_USE_SAM_DUE
#endif
#define ESP_AT_USE_SAM_DUE        true
#endif

#if ( defined(CORE_TEENSY) && !( defined(__MKL26Z64__) || defined(__AVR_AT90USB1286__) || defined(__AVR_ATmega32U4__) ) )
#if defined(ESP_AT_USE_TEENSY)
#undef ESP_AT_USE_TEENSY
#endif
#define ESP_AT_USE_TEENSY         true
#endif

#if ( defined(STM32F0) || defined(STM32F1) || defined(STM32F2) || defined(STM32F3)  ||defined(STM32F4) || defined(STM32F7) )
#if defined(ESP_AT_USE_STM32)
#undef ESP_AT_USE_STM32
#endif
#define ESP_AT_USE_STM32      true
#endif

#if (ESP_AT_USE_NRF528XX)

#if defined(NRF52840_FEATHER)
#define BOARD_TYPE      "NRF52840_FEATHER_EXPRESS"
#elif defined(NRF52832_FEATHER)
#define BOARD_TYPE      "NRF52832_FEATHER"
#elif defined(NRF52840_FEATHER_SENSE)
#define BOARD_TYPE      "NRF52840_FEATHER_SENSE"
#elif defined(NRF52840_ITSYBITSY)
#define BOARD_TYPE      "NRF52840_ITSYBITSY_EXPRESS"
#elif defined(NRF52840_CIRCUITPLAY)
#define BOARD_TYPE      "NRF52840_CIRCUIT_PLAYGROUND"
#elif defined(NRF52840_CLUE)
#define BOARD_TYPE      "NRF52840_CLUE"
#elif defined(NRF52840_METRO)
#define BOARD_TYPE      "NRF52840_METRO_EXPRESS"
#elif defined(NRF52840_PCA10056)
#define BOARD_TYPE      "NORDIC_NRF52840DK"
#elif defined(NINA_B302_ublox)
#define BOARD_TYPE      "NINA_B302_ublox"
#elif defined(NINA_B112_ublox)
#define BOARD_TYPE      "NINA_B112_ublox"
#elif defined(PARTICLE_XENON)
#define BOARD_TYPE      "PARTICLE_XENON"
#elif defined(MDBT50Q_RX)
#define BOARD_TYPE      "RAYTAC_MDBT50Q_RX"
#elif defined(ARDUINO_NRF52_ADAFRUIT)
#define BOARD_TYPE      "ARDUINO_NRF52_ADAFRUIT"
#else
#define BOARD_TYPE      "nRF52 Unknown"
#endif

#define EspSerial Serial1

#elif defined(ESP_AT_USE_SAMD)
#if defined(ARDUINO_SAMD_ZERO)
#define BOARD_TYPE      "SAMD Zero"
#elif defined(ARDUINO_SAMD_MKR1000)
#define BOARD_TYPE      "SAMD MKR1000"
#elif defined(ARDUINO_SAMD_MKRWIFI1010)
#define BOARD_TYPE      "SAMD MKRWIFI1010"
#elif defined(ARDUINO_SAMD_NANO_33_IOT)
#define BOARD_TYPE      "SAMD NANO_33_IOT"
#elif defined(ARDUINO_SAMD_MKRFox1200)
#define BOARD_TYPE      "SAMD MKRFox1200"
#elif ( defined(ARDUINO_SAMD_MKRWAN1300) || defined(ARDUINO_SAMD_MKRWAN1310) )
#define BOARD_TYPE      "SAMD MKRWAN13X0"
#elif defined(ARDUINO_SAMD_MKRGSM1400)
#define BOARD_TYPE      "SAMD MKRGSM1400"
#elif defined(ARDUINO_SAMD_MKRNB1500)
#define BOARD_TYPE      "SAMD MKRNB1500"
#elif defined(ARDUINO_SAMD_MKRVIDOR4000)
#define BOARD_TYPE      "SAMD MKRVIDOR4000"
#elif defined(ARDUINO_SAMD_CIRCUITPLAYGROUND_EXPRESS)
#define BOARD_TYPE      "SAMD ARDUINO_SAMD_CIRCUITPLAYGROUND_EXPRESS"
#elif defined(__SAMD21G18A__)
#define BOARD_TYPE      "SAMD21G18A"
#elif defined(__SAMD51G19A__)
#define BOARD_TYPE      "SAMD51G19"
#elif defined(__SAMD51J19A__)
#define BOARD_TYPE      "SAMD51J19A"
#elif defined(__SAMD51J20A__)
#define BOARD_TYPE      "SAMD51J20A"
#elif defined(__SAMD51__)
#define BOARD_TYPE      "SAMD51"
#else
#define BOARD_TYPE      "SAMD Unknown"
#endif

#define EspSerial Serial1

#elif defined(ESP_AT_USE_SAM_DUE)
#if ( defined(ARDUINO_SAM_DUE) || (__SAM3X8E__) )
#define BOARD_TYPE      "SAM DUE"
#else
#define BOARD_TYPE      "SAM Unknown"
#endif

#define EspSerial Serial1

#elif ( defined(CORE_TEENSY) )
// For Teensy 4.0
#if defined(__IMXRT1062__)
#define BOARD_TYPE      "TEENSY 4.0"
#elif defined(__MK66FX1M0__)
#define BOARD_TYPE      "Teensy 3.6"
#elif defined(__MK64FX512__)
#define BOARD_TYPE      "Teensy 3.5"
#elif defined(__MK20DX256__)
#define BOARD_TYPE      "Teensy 3.2/3.1"
#elif defined(__MK20DX128__)
#define BOARD_TYPE      "Teensy 3.0"
#elif ( defined(__MKL26Z64__) || defined(__AVR_AT90USB1286__) || defined(__AVR_ATmega32U4__) )
#error "Teensy LC, 2.0++ and 2.0 not supported"
#else
#define BOARD_TYPE      "Teensy Unknown"
#endif

#define EspSerial Serial1

#elif ESP_AT_USE_STM32

#if defined(STM32F0)
#define BOARD_TYPE  "STM32F0"
#error Board STM32F0 not supported
#elif defined(STM32F1)
#define BOARD_TYPE  "STM32F1"
#elif defined(STM32F2)
#define BOARD_TYPE  "STM32F2"
#elif defined(STM32F3)
#define BOARD_TYPE  "STM32F3"
#elif defined(STM32F4)
#define BOARD_TYPE  "STM32F4"
#elif defined(STM32F7)
#define BOARD_TYPE  "STM32F7"
#else
#warning STM32 unknown board selected
#define BOARD_TYPE  "STM32 Unknown"
#endif

// For STM32, you have to declare and enable coreresponding Serial Port somewhere else before using it
#define EspSerial Serial1

#elif (ESP_AT_USE_AVR)

#if defined(ARDUINO_AVR_MEGA2560)
#define BOARD_TYPE      "AVR Mega2560"
#elif defined(ARDUINO_AVR_MEGA)
#define BOARD_TYPE      "AVR Mega"
#else
#define BOARD_TYPE      "AVR ADK"
#endif

// For Mega, use Serial1 or Serial3
#define EspSerial Serial3

#else
#error Unknown or unsupported Board. Please check your Tools->Board setting.

#endif    //ESP_AT_USE_NRF528XX

#include "ESP_AT_Lib.h"

#define SSID        "SSID"
#define PASSWORD    "password"

ESP8266 wifi(&EspSerial);

// Your board <-> ESP_AT baud rate:
#define ESP_AT_BAUD       115200

void setup(void)
{
  Serial.begin(115200);
  while (!Serial);

  Serial.println("\nStart TCPServer on " + String(BOARD_TYPE));

  // initialize serial for ESP module
  EspSerial.begin(ESP_AT_BAUD);

  Serial.print("FW Version:");
  Serial.println(wifi.getVersion().c_str());

  if (wifi.setOprToStationSoftAP())
  {
    Serial.print("Set AP/STA Mode OK");
  }
  else
  {
    Serial.print("Set AP/STA Mode failed");
  }

  if (wifi.joinAP(SSID, PASSWORD))
  {
    Serial.println("Connect to WiFi OK");
    Serial.print("IP: ");
    Serial.println(wifi.getLocalIP().c_str());
  }
  else
  {
    Serial.println("Connect to WiFi failed");
  }

  if (wifi.enableMUX())
  {
    Serial.println("enableMUX OK");
  }
  else
  {
    Serial.println("enableMUX failed");
  }

  if (wifi.startTCPServer(8090))
  {
    Serial.println("Start TCP server OK");
  }
  else
  {
    Serial.println("start TCP server failed");
  }

  if (wifi.setTCPServerTimeout(10))
  {
    Serial.println("Set TCP server timeout 10 seconds");
  }
  else
  {
    Serial.println("Set TCP server timeout failed");
  }

  Serial.println("Done");
}

void loop(void)
{
  uint8_t buffer[128] = {0};
  uint8_t mux_id;

  uint32_t len = wifi.recv(&mux_id, buffer, sizeof(buffer), 100);

  if (len > 0)
  {
    Serial.print("Status:[");
    Serial.print(wifi.getIPStatus().c_str());
    Serial.println("]");

    Serial.print("Received from :");
    Serial.println(mux_id);
    Serial.print("[");

    for (uint32_t i = 0; i < len; i++)
    {
      Serial.print((char)buffer[i]);
    }

    Serial.println("]");

    if (wifi.send(mux_id, buffer, len))
    {
      Serial.println("Send back OK");
    }
    else
    {
      Serial.println("Send back failed");
    }

    if (wifi.releaseTCP(mux_id))
    {
      Serial.print("Release TCP ");
      Serial.print(mux_id);
      Serial.println(" OK");
    }
    else
    {
      Serial.print("Release TCP ");
      Serial.print(mux_id);
      Serial.println(" failed");
    }

    Serial.print("Status:[");
    Serial.print(wifi.getIPStatus().c_str());
    Serial.println("]");
  }
}
```
---

### Releases v1.0.0

1. Add support to **nRF52 (AdaFruit Feather nRF52832, nRF52840 Express, BlueFruit Sense, Itsy-Bitsy nRF52840 Express, Metro nRF52840 Express, NINA_B302_ublox, NINA_B112_ublox, etc.)**.
2. Add support to **Adafruit SAMD21/SAM51 (Itsy-Bitsy M0/M4, Metro M0/M4, Grand Central M4, Feather M0/M4 Express, etc.)**.
3. Add support to **STM32F, Teensy, SAM DUE**.
4. Add support to ESP32-AT shields.
5. Add debug AT command output

---

### Issues ###

Submit issues to: [ESP_AT_Lib issues](https://github.com/khoih-prog/ESP_AT_Lib/issues)

---

### TO DO

1. Fix bugs

### DONE

 1. Add ESP32-AT support
 2. Replace deprecated AT commands
 3. Add debug output with debug levels
 4. Increase TX/RX Hardware Serial Buffer size
 5. Test OK with supported boards, running Blynk, Config Portal

---

### Contributions and thanks

1. All the credits go to the original authors of the [ITEADLIB_Arduino_WeeESP8266 Library](https://github.com/itead/ITEADLIB_Arduino_WeeESP8266).

---

### Contributing

If you want to contribute to this project:
- Report bugs and errors
- Ask for enhancements
- Create issues and pull requests
- Tell other people about this library

---

### License

- The library is licensed under [MIT](https://github.com/khoih-prog/ESP_AT_Lib/blob/master/LICENSE)

---

## Copyright

Copyright 2020- Khoi Hoang

