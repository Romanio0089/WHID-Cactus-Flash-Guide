# Arduino Keyboard Libraries
The best place to find Keyboard.cpp + Keyboard.h for your language !

## What are the Keyboard.cpp and Keyboard.h used for ?
These libraries are mainly used for HID devices. 

For example, if you have a device like the Arduino LilyPad USB (WHID Cactus) with ESPloitV2, if you write for example a payload with an AZERTY (French) keyboard, and the device was originally configured with a Keyboard.cpp and Keyboard.h which is a QWERTY keyboard of some kind, payloads won't work properly and instead of outputting for example a - you asked for, it will output a / because you pressed - key on your keyboard, but the keyboard layout on the device is not the same, so, that same key, at the same location of your - key, is indeed a /. 

So, with these libraries, you can change the keyboard layout of your device. (This was an example of a possible usage with a WHID Cactus. A tutorial on how to change the WHID keyboard layout can be found down below.)

## How To Install Keyboard Libraries on Arduino IDE
Go to your Arduino IDE Keyboard Libraries directory which is usually located in "C:\Program Files (x86)\Arduino\libraries\Keyboard\src".

Make a backup of your Keyboard.cpp and Keyboard.h and delete them from the "src" folder.

Copy the Keyboard.cpp and Keyboard.h that you downloaded at the language you want from this repository to "C:\Program Files (x86)\Arduino\libraries\Keyboard\src".

The new language libraries are now sucessfully installed.

## WHID Cactus (ESPloitV2) keyboard layout change [TUTORIAL]
Before starting, you need to have Arduino IDE installed on your computer. If not, please download it here : https://www.arduino.cc/en/Main/Software.

· Open Arduino IDE

· Select Sketch - Include Library - Manage Libraries. 

· Search for "ArduinoJson" (without quotes).

· Install "ArduinoJson by Benoit Blanchon - version 5.11.0" and click "Close"   

· Download https://github.com/exploitagency/esp8266FTPServer/archive/feature/bbx10_speedup.zip

· Click Sketch - Include Library - Add .ZIP Library and select esp8266FTPServer-feature-bbx10_speedup from where you downloaded the file.

· Download/extract the ESPloitV2 repository as a zip file : https://github.com/exploitagency/ESPloitV2/archive/master.zip

· Load the "esp8266Programmer" sketch from the flashing folder that can be found in the ESPloitV2 repository you extracted.

· Select Tools - Board - "LilyPad Arduino USB".

· Select the port your device is connected to under Tools - Port.

· Upload the sketch to the device.

· Load the "ESP_Code" sketch from the flashing folder that can be found in the ESPloitV2 repository you extracted.

· Select Tools - Board - "Generic ESP8266 Module".

· Select Tools - Flash Size - "4M (3M SPIFFS)".

· Select Sketch - "Export Compiled Binary".

· Now flash the firmware to the ESP-12S chip using NodeMCU Flasher. You can also use esptool on Linux, however, I will not cover it in this tutorial.

NodeMCU Flasher (Windows users) : https://github.com/nodemcu/nodemcu-flasher

esptool (for Linux only) : https://github.com/AprilBrother/esptool

· In NodeMCU, go to config, and click on the settings icon near the green line.

· Select the new file that appeared in the ESP_Code folder that can be found in the ESPloitV2 repository you extracted. The file will have a name same or similar as "ESP_Code.ino.generic.bin".

· Then, go back to operation, and select the port the WHID Cactus is connected to then click flash.

· Finally, open the "Arduino_32u4_code" sketch from the source folder that can be found in the ESPloitV2 repository you extracted.

· Select Tools - Board - "LilyPad Arduino USB".

· Select the port your device is connected to under Tools - Port.

· Then upload the sketch to the device.

DONE !
