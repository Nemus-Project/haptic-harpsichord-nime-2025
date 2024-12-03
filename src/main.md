# TITLE

## Abstract

## Introduction

## Related Work and Motivation

## Hardware Design


### Keyboard Design
- simple
- aesthetics
- split workload
#### 3-Key Prototype
- proof of concept
- available on loan from museum
- easy access to internal structure
- 
#### Fig: Construction Design Diagram  

#### 49-Key Prototype
- problems of scale
- problems of timescale

#### Fig: Construction Design Diagram

## Electronics

- Over arching themes
  - simplicity of design 
    - Limited resources
    - easily reproducible
  - availability and lead times
  - iteration and design from distance

### Sensor choice

#### QRE1113

- previous use
- problem of what to sense
- satisfied both criteria and design restrictions

#### sensor surface

- linear gradient
- on Jack
- printed and cut on vinyl [find name]
- cut to travel size
- then to jack size
- jacks varnished on side
- alternatives
  - CNC plywood and mdf
    - problems
  - laser cut plywood and mdf
    - problems
  - 3D printed jack body
    - problems

### Arduino 

#### NanoBLE

- Nano form factor small
- allows for easy changes in chipset
- "Native USB" https://learn.adafruit.com/dude-where-s-my-com-port/native-usb-boards#
- BLE Model
  - Performative
  - BLE capabilities for MIDI BLE transmission
  - All analog pins available 
  - available at the time
  - 12-bit DAC

### EEPROM / NVRAM / FRAM

- On board available, but volatile
- retained across firmware changes
- small, 
- could have been sd card or anything else
- available
- interfaced via rotary encoder

### RGB LEDs

for problems of scale:

- locating keys
- displaying key state

### Multiplexing

problem of scale

- limited ADC channels
- ADC channels already multiplexed
- simple
- 8 channel
- THT
- 7 into 49 
  - 7 PCBS
  - each with 7 sensors

### PCB design

- EAGLE
- jack / sensor picth by board
- 7 boards adjust for pitch/spacing error
- modular, replaceable
- orientation problems
  - legs break easily
  - end mount like A.P.Mc. time consuming
  - problem
    - milling out keys
- designed from distance
- striped lines across pcbs
- problems
  - additional terminals uneeded resulted in lots of additional work
  - long cabling increase risk of breaking
- solutions
  - striping all adc lines with FFC
  - solder pads to select channel

### 3D printing

- Supports
  - Push fit
- Blinkers
- mounts
  - MacMini

### Power

- 5V 1A
- 

## Software Design

- Arduino platform
  - library support and portability
  - dependancy management
  - wide spread use
- core algorithm
  - check components connected
  - READ data from FRAM
  - select key with rotary
    - click to edit, double to save
  - current threshold and reading sent over serial and plotted
  - when over threshold send MIDI note

### Project structure

- firmware
- Keyboard
- PCB CAD

## Implementation

### Context

- in museum context
- interfacing with kontakt spitfire library
- powering
- display
  - secure storage and access
  - interface to the public

### Calibration

- sensor surface
  - printed gradient

## Conclusion

- scale
- time scale
- working at distance

## Going forward

- Velocity, aftertouch
- second jack row
- reducing latency
- alternative sensor surfaces

## Acknowledgments

- Alma Labor
  - Max
- San Colombano
  - Catalina
- uCreate
  - Simeon, Stuart, Millie
- ECA
  - Richard Collins, Billy, Connor, Cameron, Joe, Mike Boyd

## Reference