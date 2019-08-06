# [NFC模块](https://github.com/OS-Q/D16)

ESP8266 + PN532

### interface

| ESP8266 | NodeMcu/WeMos | Wiegand | PN532 | MFRC522 | RDM6300 | 
|--------:|:-------------:|:-------:|:-----:|:-------:|:-------:|
| GPIO-15 | D8            |         | SS    | SDA/SS  |         |
| GPIO-13 | D7            | D0      | MOSI  | MOSI    |         |
| GPIO-12 | D6            | D1      | MISO  | MISO    |         |
| GPIO-14 | D5            |         | SCK   | SCK     |         |
| GPIO-04 | D2            |         |       |         |         |
| GPIO-05 | D1            |         |       |         |         |
| GPIO-03 | RX            |         |       |         | TX      |

[![sites](scripts/nodeMCU.png)](http://www.OS-Q.com)

[![sites](scripts/ESP12.jpg)](http://www.OS-Q.com)

```
sudo usermod -aG  dialout  user
pip install esptool
esptool.py --port /dev/ttyUSB0 -b 921600 write_flash 0x0 ./bin/blank4mb.bin

```

```
platformio run -t clean
platformio run -e generic -t upload
platformio  device monitor
```

Restore some randomly generated user data on File System worth:

1000  userfile 
4 Bytes long UID 
4 bytes random Unix Time Stamp，"access type" 1 byte integer "1" or "0".
Total 122,880 Bytes

At least 1000 unique User (RFID Tag) can be handled

### [OS-Q : Operation System for edge devices](http://www.OS-Q.com/Edge/D16)
