# ElegooCarV3
Software for my ELEGOO Smart Robot Car Kit V3.0

The idea of the project is to have an object-oriented approach to control the car, and to have all features in one implementation.

| Feature | Status |
| :--- | :--- |
| Bluetooth remote controlled | Implementation available |
| Infrared remote controlled | Implementation available |
| Manual mode, without obstacle avoidance | Simple implementation available. Only moves a short distance at a time
| Automatic mode, with obstacle avoidance | Simple implementation available. Has trouble recognizing soft obstacles, smaller obstacles, and walls if approached in angles < 45 degrees or > 135 degrees |
| Switching driving algorithm via remote control | Planned |
| Line tracking support | Planned |

## The Car

![Image of the EleegoSmartRobotCarV3.0](https://github.com/pieterbl/ElegooCarV3/blob/master/resources/EleegoSmartRobotCarV3.0.png)

## IDE

Developing using the Sloeber IDE (for Windows) "Download 64 bits Bundle" from http://eclipse.baeyens.it/stable.php?OS=Windows

## Libraries

Using following libraries:

| Library | Location |
| :--- | :--- |
| Servo | Comes with the Sloeber IDE |
| IRremote - IRremote-2.2.3.zip | http://www.arduinolibraries.info/libraries/i-rremote |


# Driving the Car

This is how driving the car looks like https://github.com/pieterbl/ElegooCarV3/blob/master/ElegooCarV3.ino

## Driving with Bluetooth

The bluetooth app can be found at the below listed locations:

| Provider | Location |
| :--- | :--- |
| Google, Andriod | https://play.google.com/store/apps/details?id=com.femtoapp.rootsence.bleutils |
| Apple, iPhone | https://itunes.apple.com/gb/app/elegoo-ble-tool/id1195318538 |

The bluetooth app must be configured in the following way:

| Left Column | Middle Column | Right Column |
| :--- | :--- | :--- |
| Half Left (\\)  | Forward (F) | Half Right (/) |
| Left (L)  | Stop (S) | Right (R) |
| _empty_ | Backward (B) | _empty_ |
| _empty_  | _empty_  | _empty_  |



# Trouble Shooting

## avrdude: stk500_getsync() attempt 10 of 10: not in sync: resp=0x00

Lots of articles on this in the Internet. For me, it means the bluetooth receiver must be removed from the car. It is preventing the upload of a new program version to the Arduino.

```
LaunchingC:\_SloeberV4.1\/arduinoPlugin/packages/arduino/tools/avrdude/6.3.0-arduino9/bin/avrdude -CC:\_SloeberV4.1\/arduinoPlugin/packages/arduino/tools/avrdude/6.3.0-arduino9/etc/avrdude.conf -patmega328p -carduino -PCOM3 -b115200 -D -Uflash:w:C:\_DATA\Dropbox\private\sloeber-workspace\ElegooCarV3/Release/ElegooCarV3.hex:i 
Output:
avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 2 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 3 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 4 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 5 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 6 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 7 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 8 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 9 of 10: not in sync: resp=0x00
avrdude: stk500_getsync() attempt 10 of 10: not in sync: resp=0x00

avrdude done.  Thank you.

/arduinoPlugin/packages/arduino/tools/avrdude/6.3.0-arduino9/bin/avrdude finished
upload done
```

# My References
| Topic | Pointer |
| :--- | :--- |
| Github Markdown Guide - General | https://guides.github.com/features/mastering-markdown/ |
| Github Markdown Guide - GitHub Flavored | https://help.github.com/articles/basic-writing-and-formatting-syntax/ |
| Github Markdown Guide - GitHub Flavored - Creating and highlighting code blocks | https://help.github.com/articles/creating-and-highlighting-code-blocks/ |


