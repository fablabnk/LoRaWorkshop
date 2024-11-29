This repo is a super-mimimal guide to getting up and running with Heltec LoRa WiFi boards using Arduino IDE 2. The aim is to get the board you have been given to flash with the simple factory test example, so that you can begin exploring its possibilties. We will work in teams with either a WiFi LoRa 32 (V2) or WiFi LoRa 32 (V3) board with the end goal to get the boards sending and receiving to each other

# Getting Started

- Boot up a lab PC from scratch
- Choose the Ubuntu option from the startup menu
- Choose the admin account and ask an admin to enter the password

# Clean Out Existing Arduino Libraries

- Open terminal and clean out any existing Arduino libraries that might cause conflicts

```
cd ~/Arduino/Libraries
rm -rf */
```

# Install Arduino IDE 2

- Go to https://www.arduino.cc/en/software
- Download `Linux AppImage 64 bits (X86-64)`
- Open terminal, move Arduino IDE AppImage to a better place, give it executable rights, then run it, as follows

```
cd ~/Downloads/
chmod 777 arduino-ide_2.3.3_Linux_64bit.AppImage
sudo mv arduino-ide_2.3.3_Linux_64bit.AppImage /opt
cd /opt
./arduino-ide_2.3.3_Linux_64bit.AppImage
```
# Install Heltec Board

- In File -> Preferences -> Additional boards manager URLs, add `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/releases/download/0.0.7/package_heltec_esp32_index.json`
- Close Preferences dialogue
- In Tools -> Board, choose `HelTec ESP Series Dev-boards`, then the correct version of your board
	- For V3: `WiFi LoRa 32 (V3) / Wireless Shell (V3) / Wireless stick lite (V3)`
	- For V2: `WiFi LoRa 32 (V2)`
- In Tools -> Port, choose `/dev/ttyUSB0` (or whichever port appears in this menu when you connect your device by USB cable)
- In File -> Examples, a list of examples code sketches should have appeared for the board you just selected i.e. 'Examples for [name of board]'. Important: Only choose examples from this list, not any other place!
- From the examples list, go to Heltec-Example -> Factory Test and choose the correct `WiFi_LoRa_32_Vx_FactoryTest.ino`, where 'x' is the version of your board (2 or 3)
- With your device connected, click the Upload button marked with a right facing arrow (e.g. ->)

# Go Further

Explore the other examples, in particular the ones in File -> Examples -> HelTec Example -> LoRaBasic, which allow a device to be setup as a sender, received or to pingpong
