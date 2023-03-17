https://esphome.io/
https://hub.docker.com/r/esphome/esphome

https://esphome.io/components/esp32_camera.html
https://esphome.io/components/esp32_camera_web_server.html

https://esphome.io/guides/faq.html?highlight=docker#docker-reference

## Running the container

docker-compose up

http://0.0.0.0:6052


## ESP32-CAM-HANS-A

esphome_1  | 2023-03-17 07:47:32,558 INFO Running command 'esphome --dashboard run /config/esp32-cam-hans-a.yaml --device OTA'

Compile
```
INFO Reading configuration /config/esp32-cam-hans-a.yaml...
WARNING GPIO0 is a Strapping PIN and should be avoided.
Attaching external pullup/down resistors to strapping pins can cause unexpected failures.
See https://esphome.io/guides/faq.html#why-am-i-getting-a-warning-about-strapping-pins
INFO Generating C++ source...
INFO Compiling app...
Processing esp32-cam-hans-a (board: esp32dev; framework: arduino; platform: platformio/espressif32 @ 5.2.0)
--------------------------------------------------------------------------------
HARDWARE: ESP32 240MHz, 320KB RAM, 4MB Flash
 - toolchain-xtensa-esp32 @ 8.4.0+2021r2-patch3
LDF: Library Dependency Finder -> https://bit.ly/configure-pio-ldf
Dependency Graph
|-- AsyncTCP-esphome @ 1.2.2
|-- WiFi @ 2.0.0
|-- FS @ 2.0.0
|-- Update @ 2.0.0
|-- ESPAsyncWebServer-esphome @ 2.1.0
|   |-- AsyncTCP-esphome @ 1.2.2
|-- DNSServer @ 2.0.0
|-- ESPmDNS @ 2.0.0
|-- noise-c @ 0.1.4
|   |-- libsodium @ 1.10018.1
RAM:   [=         ]  13.8% (used 45360 bytes from 327680 bytes)
Flash: [======    ]  55.6% (used 1020729 bytes from 1835008 bytes)
========================= [SUCCESS] Took 3.84 seconds =========================
INFO Successfully compiled program.
esptool.py v4.5.1
Serial port /dev/ttyUSB0
Connecting......
Chip is ESP32-D0WD-V3 (revision v3.0)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: e0:5a:1b:aa:eb:8c
Uploading stub...
Running stub...
Stub running...
Changing baud rate to 460800
Changed.
Configuring flash size...
Auto-detected Flash size: 4MB
Flash will be erased from 0x00010000 to 0x0010afff...
Flash will be erased from 0x00001000 to 0x00005fff...
Flash will be erased from 0x00008000 to 0x00008fff...
Flash will be erased from 0x0000e000 to 0x0000ffff...
Compressed 1026496 bytes to 674489...
Wrote 1026496 bytes (674489 compressed) at 0x00010000 in 15.7 seconds (effective 521.8 kbit/s)...
Hash of data verified.
Compressed 17440 bytes to 12127...
Wrote 17440 bytes (12127 compressed) at 0x00001000 in 0.6 seconds (effective 239.8 kbit/s)...
Hash of data verified.
Compressed 3072 bytes to 144...
Wrote 3072 bytes (144 compressed) at 0x00008000 in 0.1 seconds (effective 328.0 kbit/s)...
Hash of data verified.
Compressed 8192 bytes to 47...
Wrote 8192 bytes (47 compressed) at 0x0000e000 in 0.1 seconds (effective 448.6 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting via RTS pin...
INFO Successfully uploaded program.
INFO Starting log output from /dev/ttyUSB0 with baud rate 115200
```


## Various

```
dmesg --follow

[13871.404463] usb 1-3: new full-speed USB device number 16 using xhci_hcd
[13871.553784] usb 1-3: New USB device found, idVendor=1a86, idProduct=7523, bcdDevice=81.34
[13871.553803] usb 1-3: New USB device strings: Mfr=0, Product=2, SerialNumber=0
[13871.553811] usb 1-3: Product: USB Serial
[13871.560131] ch341 1-3:1.0: ch341-uart converter detected
[13871.560936] usb 1-3: ch341-uart converter now attached to ttyUSB0
[13872.164509] input: BRLTTY 6.5 Linux Screen Driver Keyboard as /devices/virtual/input/input25
[13872.281156] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1
[13872.281779] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0
[13872.281816] ch341 1-3:1.0: device disconnected
```

```
$ lsusb
Bus 001 Device 020: ID 1a86:7523 QinHeng Electronics CH340 serial converter
```

## /dev/ttyUSB0

https://askubuntu.com/questions/1403705/dev-ttyusb0-not-present-in-ubuntu-22-04

`sudo apt remove brltty`