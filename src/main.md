# TITLE

## Abstract

With the advent of digital musical instruments in the 20th Century there has been a decoupling between interface and sound generation when playing. Consequently, aspects of the sensory experience of playing have been lost, namely the sensation of vibration and mechanical impedance that a traditional musical instrument provides.

The project look at restoring tactile and haptic response of 17th century harpsichords for an exhibition at the musical instrument museum San Colombano in Bologna. 

Project was also designed to allow others to easily recreate and iterate on the designs.

First a small cross-sectional model was used as a proof of concept. Once a sensing system was decided upon, a larger 49-key scale model was commissioned with and then built by luthier Roberto Livi. The models are designed to provide only a tactile and haptic response for the player. A sensor system was installed into the model and messages were sent to computer that triggered sounds from a sample library which the player listens to through headphones.
The paper looks at the design decisions, processes, and considerations to be made when undertaking a project of this kind.

Overview of fabrication methods, techniques that can be employed. Finally a discussion of the limitations and areas in which the core project can be improved and developed further.


## Introduction

With the advent of digital musical instruments in the 20th Century there has been a decoupling between interface and sound generation when playing. Consequently, aspects of the sensory experience of playing have been lost, namely the sensation of vibration and mechanical impedance that a traditional musical instrument provides.

In this context, a ‘traditional’ instrument is one whose interface for generating sound and the sound generating mechanism are fundamentally coupled. A piano requires a key press which triggers a hammer, which strikes a string which vibrates a body and air cavity. This system is tied together and cannot be separated. A synthesizer, be it a theremin, a control voltage synthesizer, a MIDI controller, these are all instruments whose interface are decoupled from their sound generation.
This decoupling presents a problem that then needs to be addressed. How do we re-introduce this dimension to the experience of playing a musical instrument? How do we, and is it possible to, parameterise and preserve this experience? This is central problem that is trying to be solved in [1, 2].

This is particularly pertinent as it relates to conservation of musical instruments, as they represent both historic objects, but also tools for creating music. Historical musical instruments present an interesting problem for cultural heritage as they are both a physical object but also a tool for making music. This begs the question, can we use haptics to preserve experiences of the past? The proposed project intends to develop further the methodologies implemented in musical haptics projects [3] such as [2]. The final outcome will be to create a framework for digital conservation of historic musical instruments such as the 1638 Ioannes Ruckers and the 1646 Ioannes Couchet double-manual harpsichords as referenced in the NEMUS project [4].

Systems exist already for the conversion of piano keyboard. The Yamaha disklavier, the Don Buchla designed MOOG Piano Bar, Bosendorfer, PNOscan by QRS focus on reproduction. These same systems could be applied to a harpsichord, but the limitation is a single data stream per key.



- existing sysetms
  - Yamaha Disklaviare
  - Bosendorfer
    - 290SE
    - CEUS
  - Don Buchla / Moog Piano Bar
  - PNOscan MIDI 9 QRS Music
    - PNOmation
  - Piano Disc


### Motivations

The project was  carried out in collaboratoiun with San Colombano. The results of the project would be presented as an interactive exhibition for the public.

#### the problem

Central philosophy of the Tagliavini Collection is that the instrument should remain playable to the public. The condition of some instruments is such that restoration would required a replacement of vast majority of the instrument, would be too costly, would risk the instrument given its fragility, or all of those in combination.

This is not an uncommon problem faced by musical instrument museums worldwide. The central question the project tries to answer is "how do we conserve musical instruments in order to continue interacting with them"

#### the solution

The approach taken was to recreate the interface of these instruments not for acoustics purposes be purely for the mechanical resoponse. As exhibition for the general public in a musical instruments there were aesthetic and functional constraints placed on the design of the interface.

#### Criteria

A keyboard interface that provides a comparable physical response to a harpsichord. Notes should be assigned per jack and not per key.

#### Design Constraints

- no electronics should be visible.
- it should be robust and reliable, easily maintained by museum staff without complex technical processes
- it should not augment or fix the mechanics, but present them with their original limitation

Another constraint was that the design of the sensor system and the model keyboard would have to carried out at a distance in separate workshops. Time constraints meant the keyboard was being fabricated for a sensor that did not yet exist. 


Accomodations were made in the design to allow for as much flexibility as possible. This also meant that designs for the eletronics would have to include a deal of flexibility in how they might be installed. Surplus space was added into the design of the internal chamber of the model \FIGURE, but there was still a limit given the structural and aesthatic requirements.

#### Sensor Criteria

A set of criteria was drawn to which the final sensor system would have to satisfy. This criteria was used as a means of evaluating the feasability throughout the prototyping phase.

- Non-invasive: The sensor system should not require major modifications to the interface on which it is installed.
- Low Latency: Reading sensors and then triggering an output should have a low latency. Using [paper on latency] a target was set as X ms with an upper limit set to 25ms beyond which the sensors would be deemed unusable
- Reliable: Data obtained should be reliable and accurate enough not to result in false positives or false negatives without extensive filtering
- Scalable: The system should be scalable both economically and temporally. Given the open soucre nature of the porject, it could not be prohibitvely expensive to carry out. Also any system that would work on a single key would have to scale financially to  potentially 50 or more. The time required to install and calibrate the sensors would also have to scale. 
- Expandable: Any sensor system should be functionally expandable to allow for the usage of the data for control over other parameters.


#### Triggering a note

For the first iteration the data from the sensor would simply be used to test when a threshold had been passed. On passing the threshold a message would be sent to trigger the playback of a corresponding note. 

The message format covered in \section

## Related Work and Motivation

## Hardware Design

The hardware was designed with the xx in mind.

Using a similalr apporach to @HapticKey the first step was to fabricate or procure a model of a single working key. San Colombano provided a model 3-key of a harposchord mechanism by Graziano Bandini \FIGURE. The 3-key model was used a test-bed for potential sensors while designs were drawn for a full-scale model. The cross-sectional nature of the model meant it was easy to fit and remove sensors. Small size meant that it would also be easy to transfer between workshops. 

3-key model also had a sliding jack rail which allowed for easy disengagement of the physical mechanical response, which allowed for some preliminary tests on the presence and absence of mechanism.

### Failed sensors

A number of sensors were tried before the final system was decided upon. An inertial measurment unit (IMU) was mounted to a single key which contained a 6 degrees of freedome acceleromoetr and gyroscope. There was a consistent set of conditions to trigger sound, but this was not easily differntiable when other keys were played. The fitting time and cost of a single IMU could b reduced when purchased in bulk but was far greater than other systems considered.

A reed sensor and a hall sensor were mounted and magnets embedded within the jacks. Adjusting the hieight of the sensor provided a reliable means of detecting a threshold, inparticular the hall sensors which could be partially calibrarted physically and also in softwrae. The time taken to calibarte a single key was time consuming. Ideally each sensor would be placed on a thread for adjustment, but given the constraints on the internal space it was decided any adjustment of heights would likely mean an unnacceptable length of time to install and calibrate. Embedding magnets into the jacks was also did not satisfy the criteria of being scalable and non-invasive.

Light dependant resistor mounted to the jack rail. as jacks were pressed less light would be let through. Usable data but very dependant on lighting conditions. Modifying the jack also did not satisfy the non-intrusive criteria and the placement outside the internal chamber of the model meant hiding electronics would be more difficult.

Finally, force sensitive resistors placed under the jack of each key was considered but was never implemented. The sensors were to be placed under each jack either above or below the padding on which the bottom of the jack rests. Further discussion of this apporach is in \section.

### Keyboard Design

- simple
- aesthetics
- split workload

The desicion was made to design the elctronic sna dthe model keyboard in tandem. Allow for quicker development time and iteration on the idea. Likely the first implementation would need re-designed and redesiginng the electronics to fit the form of the keyboard was more cost effective than building or carrying out major modifications to the model.

The model was designed to have two internal chambers a front and rear. The front and back that was xxx by yyy by 370mm between the faceplate and the jacks. The TONGUE THAT GOES INTO SLOT divides the chamber though a small gap between the under side of the soundboard and the key guides. The key guide needs to be deep enough to allow for the full movement of the key and stop the key becoming unseated. The chamber then extends to a support wall which divides the front and rear.

Discussion of spatial constraints and affects on  electyronics design and installation is covered in \section{setup}

The rear chamber was desigbned to house comonents for audio processing, which is discussed further in \section

https://github.com/Nemus-Project/haptic-harpsichord-nime-2025/issues/Nemus-Project/haptic-harpsichord-nime-2025/images/disegno.pdf

For the initial prototyping stage, modifying an existing harpsichord was considered though ultimately discarded. An existing instrument would have provided a test for scaling the electronics, but internal measurments and layout would have been too different. A harpsichord that was economic enough to be deconstructed would also have been of a more modern mechanical design and not of the design that was being recreated with the model. Prototyping stage would likely be invasive and damage or heavy modification likely. As such it was not a good use of funds as a modern instrument fit for destruction did not offer benefits that the small model with easy internal access did not already provide.

#### 3-Key Prototype

- proof of concept
- available on loan from museum
- easy access to internal structure
  
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


#### QRE1113

Following from the work in \cite{McPherson1} \cite{McPherson2} we tested a system using the Fairchild QRE1113 \datasheetfigue. 
The QRE1113 is a combination infrared LED and phototransistor sensitive to IR light. The phototransistor of QRE1113 provides data on how much light is present
and in particular how much light is being relfected from a surface. Since refelected light will be proportional to the distance of a surfcae it is a good, close proximity, distance sensor.
Distance is the way in which the instruments in \citeMcpherson1&2 function as well the Moog Piano Bar from which it too inspiration.

The limitation for taking a distance approach is that there is not one but 2 jacks per key. For each jack to be measured indepeedntly the data would need tp com fropm the jacks themselves.

They _could_ be used and individual trigger points set in calibration, but this creates new problems. 

- The triggering would need to be bespoke for every key as fluxuations in the dimensions of every piece mean that the threshold would be different.
  - Moving a problem into additional time in the calibtraryoin setup phase.
- Remebering the constraint that system isshould noyt fix problem, there would be no easy way to tell if a jack had nbot reseated. 
  - In playing a harpihchord when the jack  does not go to its rest position, not note would play. This fault should be carried over intp the final instrument.


Another common application of the QRE1113 is within line following robots, where an array of QRE1113s ar used in conjunction with black tape along which some motorised system can following

Applied to the jacks was a greyscale gradient printed the length full travel range of the jack.

For the first iteration this was performed on an inkjet printer and double-sided tape. 
For the final iteration the stickers were printed on (Coala, 1D 100 Gloss P, gloss, white, permanent adhesive, 300g/m2, 100 µm, 1370mm x 50.00m, Solvent/Latex/UV) using a HP Latex 115 and then cutout with a Summa 150 roll cutter.
The printer and roll cutter greatly reduced the manual labour for cutting stickers meaning the process would scale from the 3-key to the 49-key model.




- previous use
- problem of what to sense
- satisfied both criteria and design restrictions
- usage
  - Sweet spot is around 6mm distance
- 


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

There would need to be the ability to store values on non-volatile memory so that the electroincs could be powered-down without losing data.

Adjusting the values through firmware would not have been flexible or practical. Instead an Ferroelectric RAM unit was chosen and connected using an SPI interface. 
NVRAM or EEPROM would have sufficed and the FRAM was primarily chosen for it's ready availability. 

Most microcontrollers have some variety of non-volatile program memory that can be read and writ accessed but in most cases this memory is cleared during compilation and re-flashing.
The small cost was far outweighed by the potential for data loss if using onboard RAM.

_It is worth noting that the FRAM model chosen stopped being available during the project, meaning any future iteration would need to adjust for another board in firmware_

The firmware was structure in a way that the interface could be changed so long as the code required for any other board would comply with function arguments and outputs.
Worth noting the fragility and volatility when designing this kind of project and how easily it is for them to become broken.

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

#### Sensor board

- jack / sensor pitch by board
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

#### controller board

- mount for nano  to allow switching
- initially push fit 2.54mm header
  - not a secure fit
- JST-PH used
  - crimping required custom cables
    - could be assembled from other cables
    - length limited
  - prohibitevly expensive to crimpers
  - 3D print helper to allow for crimping with generic crimpers

### 3D printing

- Supports
  - Push fit
  - adjustable for best average placement
- Blinkers
  - reduce noise from other senors
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

### Installation

The electronic components were partly pre-assembled at the university of Edinburgh. Though all measurments were known ahead, enough flexibiliyty was needed to allow for proboems to solved in situ.

The final assembly took place at the NEMUS lab at the univerity of bologna over the final week in October 2024 for delivery at San Colombano  for exhibition in the first week of November in 2024.

A misreading in the original clearance between the keys and the PCB meant that the keys wer block entirely from moving. A 10mm by 15mm section was milled out of each lke \FIGURE to create extra clearance. 
The milling required the removal, shortening and refitting of the leather pads for the jacks \FIGURE. The extra work added an extra day to the full install.

A redesign of the PCBs meant that removing the material would no longer be necessary.

The PCBs shared power and data lines for components with the exception of the output from the multiplexer. Ribbon cable was cut to size to allow for some room to readjust the distance of the sensors from the jacks.
The data signals from each PCB were connected using a separate cable loom. Soldering cables and inspecting each join required another day work. This did allow for readjustments to the positon of the controller board
Measurements of the rear chamber did not match with the MacMini that was to be used a different layout was decided for fitting the controller board/ Cutting cables to size allowed for a great deal of felxibility but at the cost of time. 
After the first install it was clearer what constraints were in place for fittig and an alternative wiring system using flat flex cable was implement (discussed in \section)

Fitting PCBs required the removal of all keys. The support brackets were assembled and screwed into the the underside. With the harpsichord on it's back the sensors were tested to ensure an expected range.
Self-tapping round head screws were used to to attach the brackets. The screws were not over tightened to allow for brackets to move. The brackets were not easily adjusted once the key were replaced. 
Adjusted to a best average with subsequent adjustment carried out on the microcontroller.

After fitting the PCBs preliminary calibration was carried out. This mainly done to test the work flow of calibration with those unfamiliar with the system. Adjustments were made to the firmware to accomodate a new workflow
Usage of addressable LEDs became vital as it allowed for easy identification of the key being calibrated. They were also used to identify any keys whose current reading was beyond what was expected.

The rotary encoder was used as the interface to select a key, adjust it's threshold and update the Ferroelectric RAM (FRAM) with new values.

A process was implemented where the key was selected by playing, but this caused problems in situations where the data was unusual due to misalignement of the sensors

This would likely be a better system for when the keyboard was fully operational 

The thresholds were calibrated visually utilising the serial plotter of the Arduino IDE and MIDI was confirmed using the open source MIDI Monitor (https://github.com/krevis/MIDIApps).


 - partial pre-assembly
 - handsolder components
   - analog lines
 - connecting supports
 

### Context

- in museum context
- strings damped
- headphones
- interfacing with kontakt spitfire library
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
- limitations
  - latency
  - deprecation
    - software
      - EAGLE
    - hardware
      - FRAM

## Going forward

- Velocity, aftertouch
- second jack row
- reducing latency
- alternative sensor surfaces
- ESP-IDF
  - latency half
  - workload high

### improvements

- avoid soldering cabling
- power indicators on pcbs
  - debug if problem is power related

## Acknowledgments

A project of this breadth developed across 3 institutes and 2 countries cannot be carried without the support and technical knowledge of many skilled and passionate people.

We acknoweldge the invaluable contrinbutions ofç

- Unibo
  - Alma Labor
    - Massimiliano Fraulini and the staff of ALma Labor at the Yiversità of bologna for their 3D printing expertise and generosity with electronics equipment
  - Fisica Tecnica
    - Maurzio Chendi Fabrizio Casarini, Giulio Severo and Barbara Costantini
- San Colombano
  - Catalina Vincens
  - Roberto Livi
- Edinburgh
  - uCreate
    - Simeon, Stuart, Millie, and Ruth of uCreate at the Univeristy of Edinburgh for their support with soldering facilities.
  - ECA
    - Richard Collins and the Digital Making Staff at the Edinburgh College of Art for 3D printing instruction and CNC support.
    - Joe Hathaway of Digital Development at the College of Art for providing electronics components

## Reference