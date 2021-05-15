# ECE 263 Breakout Board Version 1
This repository is the public repo for the version one board for ECE160/263 "the White Board"
it contains the original board files, and renders of the Schematic and Pcb (top and bottom) hosted here for easy reference.

This board was originally designed to mate with a standard arduino uno. but will also work with and atmel Xplained mini 328p or pb


## Potentiometers
Three potentiometers are connected across the power rail with wipers connected to the Analog to Digital Converter (ADC) pins.
- Arduino pins: A0, A1, A2
- 328p pins PORT: C0, C1, C2

## Buttons
Three Momentary buttons are hooked up the processor to pull the inputs to ground when pressed.
Pull up resistors are onboard so the internal pull ups of the 328p/328pb don't need be activated.
- Arduino pins: A3, A4, A5
- 328p pins: PORT C3, C4, C5

## Seven Segment Display
A socket is provided for a 4 digit seven segment display with common Cathodes.
Jumpers 3,4,5 must be set to enable either the seven segment display or the RGB led. Only one can be used at a time.

- Digit Enables:
 - Arduino: Digital 8,9,10,11
 - 328p: PORTB 0,1,2,3
- Anodes (abcdefg.):
 - Arduino: Digital 0,1,2,3,4,5,6,7
 - 328p: PORTD 0,1,2,3,4,5,6,7

## RGB led
A 10MM RGB Common Anode LED is included on the expansion board but must be selected by moving jumpers 3,4,5.

Color Cathodes (BGR):
- Arduino: Digital 9,10,11
- 328p: PORTB 1,2,3
Anode:
- Arduino: Digital 12
- 328p: PORTB 4

## Speaker
A speaker is connected to Digital 13/ PORTB5.

The less this annoying buzzer is used, the better.
its constant buzzing is what led to a complete redesign of this board...

## Expansion Connector
3 external connections are provided on portC/analog pins 3,4,5.
these have external pullups making them useful for a thermistor or external buttons.
