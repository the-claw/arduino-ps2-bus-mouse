# Arduino PS2 to bus mouse adapter

Allows the use of a PS2 mouse (or USB mouse operating in PS2 compatibility mode) on systems with a bus mouse (quadrature) interface.

This sketch is based on an [article](https://ezcontents.org/acorn-arduino-ps2-mouse-adapter) by ezContents, with the following changes:

* The mouse is power-cycled during the initialisation phase, which fixes USB mice hanging at start-up.
* The initialisation phase is retried repeatedly until successful.
* More accurate translation of PS2 mouse position changes to bus mouse signals for better cursor movement.

## Building
Copy the contents of the `libraries` directory to your user's Arduino libraries directory (usually ~/Arduino/libraries), then verify/upload the sketch using the Arduino IDE.

## Notes
This sketch was tested on an Arduino Nano, with a Genius USB optical mouse and Acorn Archimedes A3000 computer. It should work with any system that requires quadrature-encoded mouse signals (usually a 9-pin mini DIN connector).

The power-cycling feature is optional, and enabled by connecting the PS2/USB mouse +5V line to pin 12 of the Arduino (instead of the +5V pin of the Arduino). Note that the Arduino digital pins can only source around 40mA of current, so the mouse must draw less than that or a transistor buffer will be required.

