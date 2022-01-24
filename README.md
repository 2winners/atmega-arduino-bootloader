# atmega-arduino-bootloader
Board and HOWTO to upload bootloader onto atmega 328P-PU 328P-AU 328P


hardware  connections
ID  USBasp ARD > Target 328p-au
VCC:  2     5V  > pin 4 & 18
GND:  4     GND > Pin 5 & 21
MOSI: 1     11  > Pin 15
MISO: 9     12  > pin 16
SCK:  7     13  > pin 17
RST:  5     10  > pin 29

Xtal1:          > pin 7
Xtal2:          > pin 8

or make the board using the uploaded files on a UNO 


1) open arduino.exe
2) file> preferences>
3) into " additonal board manager URLs:" paste link : https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json 
4) click on : " Show verbose output during : upload" if not already selected
5) click OKE
6) tools > Board > Board manager
7) scroll down ( probably to end) find "miniCore" 
8) install "MiniCore"
9) close Board manager

for programing you can use a UNO or any other boards as programmer but you can also use a usb to ISP converter 
10 A.1) Upload "ArduinoISP.ino" onto arduino to be used as intermediary for bootloading
10 A.2) Set Tools > programmer > Arduino as ISP (Minicore);
10 B.1)using a USBasp make sure to have the right driver if not working properly try installing LIBUSBK using https://zadig.akeo.ie
10 B.2) Set Tools > programmer > USBasp (minicore)

11) Tools > Board > minicore > Atmega328
12) Tools > Board > Select clock used and varriant
13) NOW make the connection to the chip using the before mentioned wiring 
14) plug in device
15) Tools > Load bootloader

16) if correct " Done uploading " should show 
as well as : 
Reading | ################################################## | 100% 0.00s

avrdude: verifying ...
avrdude: 1 bytes of lock verified

avrdude done.  Thank you.

IF any error check if chip is placed correctly and or making good contact most upload errors are bad connections 

