# ECE 263 Breakout Board Version 3
This repository is the public repo for the version one board for ECE263 "The Red Board"
It is targeted towards the Atmel Xplained Mini328pb not all features will be available if connected to an Arduino.
this repo contains the original board files, and renders of the Schematic and PCB (top and bottom) hosted here for easy reference.

## Building your own
Version three was designed to be assembed automatically by the ECE department Pick and place machine or assembled by hand (in a pinch). all passives are 0805.

|part| part Number|
|---|---|
|seven segment display |LTC-5723HR|
|RGB LED | ASMB-MTB0-0A3A2|
|Buzzer |	PKMCS0909E4000-R1|
| Button| EVP-BFAC1A000|
| transistors| MMBT2222A |


## Potentiometers
Three potentiometers are connected across the power rail with wipers connected to the Analog to Digital Converter (ADC) pins.
- 328p pins PORT: C0, C1, C2

## Buttons
Three Momentary buttons are hooked up the processor to pull the inputs to ground when pressed.
Pull up resistors are onboard so the internal pull ups of the 328p/328pb don't need be activated.
- 328p pins: PORTE 0,1,2

## Seven Segment Display
A socket is provided for a 4 digit seven segment display with Common Cathodes.

- Digit Enables:
 - PORTB 0,1,2,3
- Anodes (abcdefg.):
 - PORTD 0,1,2,3,4,5,6,7

## RGB led
A SMD Common Anode LED is included on the expansion board.
each Cathode is connected to a PWM capable Pin.
Color Cathodes (BGR):
- PORT B3,B1,D6
Anode:
- PORT C3

## Speaker
A SMD peizo speaker is enabled by bringing PE3 high then can be controlled by toggling PD2.
D2 is also the modulator output on the atmega328pb.

## IO Expansion Connector
3 external connections are provided on PE0,PB0,PE1.
these have external pullups making them useful for a thermistor or external buttons. they are also the processors Input Capture pins

## SPI Connector
A six pin connector is located under the seven segment display to allow the connection of a  [MAX7221 breakout](https://github.com/bveina/Max7221-Driver).
or any SPI device.
pinout:
1. MOSI0
2. MISO0
3. GND
4. VCC
5. SCK0
6. PB2 (SS0)

## I2C:registered: / TWI Expansion
a 4 pin two wire interface is broken out for connection to external devices
1. GND
2. VCC
3. SDA0/PC4
4. SCL0/PC5
