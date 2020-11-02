# SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual

:exclamation: This project provides and Interactive PDF (documentation) on how to configure stepper motor 
driver boards and how to use them with the SKR PRO V1.1 (3D printer controller) board.  This manual also 
shows the user how to connect additional equipment to the SKR PRO V1.1 Board: Raspberry Pi, BLTouch, 
BTT Smart Filament Sensor, 
PT100 sensor via Analog ADC I/O Input (PT100 Amplifier), 
PT100 sensor via Software SPI (Adafruit MAX31865 Amplifier), 
K-Type Thermocouple via Analog ADC I/O Input (Adafruit AD8495 Amplifier), 
K-Type Thermocouple via Software SPI (Adafruit MAX31855 Amplifier) and
Link to TWhite101 Instructable on how to add an EEPROM :exclamation:
```
I use Git for Windows with VScode to manage this repository.  I also use Git LFS extensions
for .pdf and .png files.

Install Git with LFS extensions: https://git-lfs.github.com/

To Download the whole repository do the following: select the "Clone or download button" and 
click on "paste to clipboard" button so you can place the URL for the GitHub repository 
to the clipboard. Now Open Git Bash.  Change the current working directory to the location 
where you want the cloned directory.
Type git clone, and then paste the URL you copied earlier.
$ git clone https://github.com/GadgetAngel/SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual.git
Press Enter to create your local clone.
Now open Window explorer to the location of local clone.
```
## The Whole Repository in .zip file is located on Google Drive at: 
https://drive.google.com/file/d/1O82o16ouSXPkhGySXl9ZE93H82mqJ-9m/view?usp=sharing

## Table of Contents:

```
Stepper Driver Jumper Configurations for SKR PRO V1.1 Board
By       @GadgetAngel

ABOUT.............................................................................................................I
Preface...........................................................................................................1
  What is a Stepper motor?........................................................................................2
  Stall Detection and Sensor-less Homing..........................................................................3
    Requirements Needed to Make Sensor-less Homing Work...........................................................3
  Introduction to LEGENDS and Common Terminology in this Manual...................................................4
POLOLU A4988......................................................................................................6
  Driver Chip Chart for POLOLU A4988..............................................................................6
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set...........7
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board8
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers
    Which Have RST&SLP Set.......................................................................................10
  The (latest release of) Marlin Setup for POLOLU A4988 Drivers..................................................15
BIQU A4988.......................................................................................................17
  Driver Chip Chart for BIQU A4988...............................................................................17
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........18
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................19
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers
    Which Have RST&SLP Set.......................................................................................21
  The (latest release of) Marlin Setup for BIQU A4988 Drivers....................................................26
DRV8825..........................................................................................................28
  Driver Chip Chart for DRV8825..................................................................................28
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........29
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................30
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Have RST&SLP Set.......................................................................................32
  The (latest release of) Marlin Setup for DRV8825 Drivers.......................................................38
BIQU LV8729......................................................................................................41
  Driver Chip Chart for BIQU LV8729..............................................................................41
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...42
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers
    Which Do Not Have RST&SLP Set................................................................................44
  The (latest release of) Marlin Setup for BIQU LV8729 Drivers...................................................50
FYSETC LV8729....................................................................................................54
  Driver Chip Chart for FYSETC LV8729............................................................................54
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...55
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set................................................................................57
  The (latest release of) Marlin Setup for FYSETC LV8729 Drivers.................................................63
LERDGE LV8729....................................................................................................67
  Driver Chip Chart for LERDGE LV8729............................................................................67
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...68
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set................................................................................70
  The (latest release of) Marlin Setup for LERDGE LV8729 Drivers.................................................76
MKS LV8729.......................................................................................................80
  Driver Chip Chart for MKS LV8729...............................................................................80
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...81
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set................................................................................83
  The (latest release of) Marlin Setup for MKS LV8729 Drivers....................................................89
FYSETC S6128 V1.1................................................................................................93
  Driver Chip Chart for FYSETC S6128 V1.1........................................................................93
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........94
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................95
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Have RST&SLP Set.......................................................................................97
  The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers............................................103
FYSETC ST820....................................................................................................107
  Driver Chip Chart for FYSETC ST820............................................................................107
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........108
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................109
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Have RST&SLP Set......................................................................................111
  The (latest release of) Marlin Setup for FYSETC ST820 Drivers.................................................117
BIQU ST820......................................................................................................122
  Driver Chip Chart for BIQU ST820..............................................................................122
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........123
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................124
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Have RST&SLP Set......................................................................................126
  The (latest release of) Marlin Setup for BIQU ST820 Drivers...................................................132
POLOLU ST820 (STSPIN820)........................................................................................137
  Driver Chip Chart for POLOLU ST820 (STSPIN820)................................................................137
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........138
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................139
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Have RST&SLP Set......................................................................................141
  The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers.....................................147
POLOLU MP6500...................................................................................................152
  Driver Chip Chart for POLOLU MP6500...........................................................................152
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers 
    Which Do Not Have RST&SLP PINS Set..........................................................................153
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set...............................................................................155
  The (latest release of) Marlin Setup for POLOLU MP6500 Drivers................................................159
POLOLU TB67S249FTG..............................................................................................163
  Driver Chip Chart for POLOLU TB67S249FTG......................................................................163
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers 
    Which Do Not Have RST&SLP PINS Set..........................................................................164
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set...............................................................................166
  The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers...........................................172
BIQU S109.......................................................................................................176
  Driver Chip Chart for BIQU S109...............................................................................176
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..177
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set...............................................................................179
  The (latest release of) Marlin Setup for BIQU S109 Drivers....................................................185
FYSETC S109.....................................................................................................189
  Driver Chip Chart for FYSETC S109.............................................................................189
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..190
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
    Which Do Not Have RST&SLP Set...............................................................................192
  The (latest release of) Marlin Setup for FYSETC S109 Drivers..................................................198
BIQU TMC2100 Stand-alone Mode...................................................................................202
  Driver Chip Chart for BIQU TMC2100 in Stand-alone Mode........................................................202
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...............................203
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...............................204
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................206
  The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode.............................211
MKS TMC2100 Stand-alone Mode....................................................................................215
  Driver Chip Chart for MKS TMC2100 in Stand-alone Mode.........................................................215
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...............................216
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...............................217
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................219
  The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode..............................224
BIQU TMC2130 (SA) Stand-alone Mode..............................................................................228
  Driver Chip Chart for BIQU TMC2130 (SA) in Stand-alone Mode...................................................228
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...............................229
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...............................230
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................232
BIQU TMC2130 SPI Mode...........................................................................................241
  Driver Chip Chart for BIQU TMC2130 in SPI Mode................................................................241
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.....................244
  Information on Sensor-less Homing for SKR PRO V1.1............................................................247
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode.....................................252
BIQU TMC2208 V3.0 (SA) Stand-alone Mode for StealthChop.........................................................266
  Driver Chip Chart for BIQU TMC2208 V3.0 (SA) in Stand-alone Mode (StealthChop)................................266
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers
    in Stand-alone Mode (StealthChop)...........................................................................267
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor 
    Drivers in Stand-alone Mode (StealthChop)...................................................................269
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (SA) Drivers
    in Stand-alone Mode for StealthChop.........................................................................273
BIQU TMC2208 V3.0 (OTP) Stand-alone Mode for SpreadCycle........................................................277
  Driver Chip Chart for BIQU TMC2208 V3.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................277
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................278
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................280
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..284
BIQU TMC2208 V3.0 UART Mode.....................................................................................288
  Driver Chip Chart for BIQU TMC2208 V3.0 in UART Mode..........................................................288
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................291
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode...............................297
FYSETC TMC2208 V1.2 (SA) Stand-alone Mode for StealthChop.......................................................306
  Driver Chip Chart for FYSETC TMC2208 V1.2 (SA) in Stand-alone Mode (StealthChop)..............................306
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................307
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................309
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop.313
FYSETC TMC2208 V1.2 (OTP) Stand-alone Mode for SpreadCycle......................................................317
  Driver Chip Chart for FYSETC TMC2208 V1.2 (OTP) in Stand-alone Mode (SpreadCycle).............................317
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................318
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................320
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (OTP) Drivers 
    in Stand-alone Mode for SpreadCycle.........................................................................324
FYSETC TMC2208 V1.2 UART Mode...................................................................................328
  Driver Chip Chart for FYSETC TMC2208 V1.2 in UART Mode........................................................328
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................331
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode.............................337
BIQU TMC2225 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................346
  Driver Chip Chart for BIQU TMC2225 V1.0 (SA) in Stand-alone Mode (StealthChop)................................346
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................347
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................349
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...353
BIQU TMC2225 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................357
  Driver Chip Chart for BIQU TMC2225 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................357
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................358
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................360
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..364
BIQU TMC2225 V1.0 UART Mode.....................................................................................368
  Driver Chip Chart for BIQU TMC2225 V1.0 in UART Mode..........................................................368
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................371
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode...............................377
BIQU TMC2209 V1.2 (SA) Stand-alone Mode for StealthChop.........................................................386
  Driver Chip Chart for BIQU TMC2209 V1.2 (SA) in Stand-alone Mode (StealthChop)................................386
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................387
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................389
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop...393
BIQU TMC2209 V1.2 (OTP) Stand-alone Mode for SpreadCycle........................................................397
  Driver Chip Chart for BIQU TMC2209 V1.2 (OTP) in Stand-alone Mode (SpreadCycle)...............................397
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................398
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................400
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (OTP) Drivers in Stand-alone Mode for SpreadCycle..404
BIQU TMC2209 V1.2 UART Mode.....................................................................................408
  Driver Chip Chart for BIQU TMC2209 V1.2 in UART Mode..........................................................408
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................411
  Information on Sensor-less Homing for SKR PRO V1.1............................................................415
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode...............................420
BIQU TMC2226 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................434
  Driver Chip Chart for BIQU TMC2226 V1.0 (SA) in Stand-alone Mode (StealthChop)................................434
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................435
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (StealthChop)...........................................................................437
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...441
BIQU TMC2226 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................445
  Driver Chip Chart for BIQU TMC2226 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................445
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................446
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
    in Stand-alone Mode (SpreadCycle)...........................................................................448
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..452
BIQU TMC2226 V1.0 UART Mode.....................................................................................456
  Driver Chip Chart for BIQU TMC2226 V1.0 in UART Mode..........................................................456
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................459
  Information on Sensor-less Homing for SKR PRO V1.1............................................................463
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 Drivers in UART Mode...............................468
BIQU TMC5160 V1.2 SPI Mode......................................................................................482
  Driver Chip Chart for BIQU TMC5160 V1.2 in SPI Mode...........................................................482
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.....................485
  Information on Sensor-less Homing for SKR PRO V1.1............................................................488
  The (latest release of) Marlin Setup for BIQU TMC5160 V1.2 Drivers in SPI Mode................................493
BIQU TMC5161 V1.0 SPI Mode......................................................................................507
  Driver Chip Chart for BIQU TMC5161 V1.0 in SPI Mode...........................................................507
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.....................510
  Information on Sensor-less Homing for SKR PRO V1.1............................................................513
  The (latest release of) Marlin Setup for BIQU TMC5161 V1.0 Drivers in SPI Mode................................518
APPENDIX A......................................................................................................532
  How to adjust the Vref on a Stepper Motor Driver board using the Potentiometer................................532
    How to Tune Stepper Motor Drivers?..........................................................................532
APPENDIX B......................................................................................................534
  For the TMC drivers what’s the difference between stand-alone mode and (“UART” or “SPI “) modes?..............534
  How to Calculate Vref for Non-TMC Stepper Motor Divers........................................................534
  How to Calculate Vref for TMC Stepper Motor Drivers...........................................................535
    Driving Current Calculation Formulas for TMC Stepper Motor Drivers..........................................536
      #1 TMC2100 with Rs = 0.110Ω (110mΩ).......................................................................536
      #2 TMC2130 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode and SPI Mode.....................................536
      #3 TMC2208 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode..................................................537
      #4 TMC2208 with Rs = 0.110Ω (110mΩ) for UART Mode.........................................................537
      #5 TMC2209 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode..................................................538
      #6 TMC2209 with Rs = 0.110Ω (110mΩ) for UART Mode.........................................................538
      #7 TMC2225 with Rs = 0.150Ω (150mΩ) for Stand-alone Mode..................................................539
      #8 TMC2225 with Rs = 0.150Ω (150mΩ) for UART Mode.........................................................539
      #9 TMC2226 with Rs = 0.150Ω (150mΩ) for Stand-alone Mode..................................................540
      #10 TMC2226 with Rs = 0.150Ω (150mΩ) for UART Mode........................................................540
      #11 TMC5160 with Rs = 0.075Ω (75mΩ) for SPI Mode..........................................................541
      #12 TMC5161 with Rs = 0.062Ω (62mΩ) for SPI Mode..........................................................541
APPENDIX C......................................................................................................542
  The (Latest Release of) Marlin Setup That Is Common to ALL Stepper Motor Drivers..............................542
    Link to BIGTREETECH SKR-PRO-V1.1 User Manual.pdf............................................................542
    Link to BIGTREETECH SKR-PRO-V1.1 Guide.pdf..................................................................542
    Link to Pronterface Software................................................................................543
    Link to How to Calibrate your 3D Printer....................................................................543
    SKR PRO V1.1 Color PIN Diagram..............................................................................560
    SKR PRO V1.1 Color Wiring Diagram...........................................................................561
    SKR PRO V1.1 Color PIN 1 Diagram............................................................................563
    SKR PRO V1.1 Color Schematic Diagram........................................................................564
    SKR PRO V1.1 Uncolored Schematic Diagram....................................................................565
APPENDIX D......................................................................................................566
  Legends for SKR PRO V1.1 Stepper Driver Jumper Configurations.................................................566
  SKR PRO V1.1 LEGEND COMMON to ALL Driver Socket Representation................................................567
  SKR PRO V1.1 LEGENDS for Driver Socket Representations and LEGENDS for Driver Chip Charts.....................571
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
      Which Have RST&SLP Set....................................................................................571
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.......574
      Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board......................................575
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers 
      Which Do Not Have RST&SLP Set.............................................................................576
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers 
      Which Do Not Have RST&SLP PINS Set........................................................................579
    SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
      in Stand-alone Mode (StealthChop).........................................................................580
    SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
      in Stand-alone Mode (StealthChop).........................................................................582
    SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers 
      in Stand-alone Mode (SpreadCycle).........................................................................583
    SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers 
      in Stand-alone Mode (SpreadCycle).........................................................................585
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.....................586
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers......................................588
    SKR PRO V1.1 LEGEND of Driver Socket Representation for SPI Capable Stepper Motor Drivers...................589
    SKR PRO V1.1 LEGEND of Driver Socket Representation for UART Capable Stepper Motor Drivers..................596
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Sensor-less Homing Capable Stepper Motor Drivers....605
  SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations.................................................611
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for Binary State Drivers without RST&SLP Set..611
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for Binary State Drivers with RST&SLP Set.....615
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for Tri State Drivers.........................619
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2209 with Sensor-less Homing...........626
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2209 without Sensor-less Homing........627
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2130 with Sensor-less Homing...........628
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2130 without Sensor-less Homing........629
APPENDIX E......................................................................................................630
  Location Of “firmware.bin” File from the Marlin Compilation for SKR PRO V1.1 Board............................630
APPENDIX F......................................................................................................633
  Links to Reference Material...................................................................................633
    Marlin Firmware Documentation...............................................................................633
    Information on Stepper Motor Drivers and Micro-stepping.....................................................633
    POLOLU A4988 and BIQU A4988.................................................................................634
    DRV8825.....................................................................................................634
    BIQU LV8729, FYSETC LV8729, LERDGE LV8729, and MKS LV879....................................................635
    BIQU LV8729.................................................................................................635
    FYSETC LV8729...............................................................................................636
    LERDGE LV8729...............................................................................................636
    MKS LV8729..................................................................................................637
    FYSETC S6128 V1.1...........................................................................................637
    FYSETC ST820................................................................................................638
    BIQU ST820..................................................................................................638
    POLOLU ST820 (STSPIN820)....................................................................................639
    POLOLU MP6500...............................................................................................639
    POLOLU TB67S249FTG..........................................................................................640
    BIQU S109 and FYSETC S109...................................................................................640
    BIQU S109...................................................................................................641
    FYSETC S109.................................................................................................641
    Marlin Firmware Documentation Specific to TMC Drivers.......................................................642
    Information Common to All TMC Drivers.......................................................................642
    BIQU TMC2100 and MKS TMC2100................................................................................643
    BIQU TMC2130................................................................................................644
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2.............................................644
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2 (Continued).................................645
    BIQU TMC2208 V3.0...........................................................................................645
    FYSETC TMC2208 V1.2.........................................................................................645
    Information Common to TMC2208 and BIQU TMC2225..............................................................646
    BIQU TMC2225 V1.0...........................................................................................646
    BIQU TMC2209 V1.2...........................................................................................647
    BIQU TMC5160 V1.2...........................................................................................647
    BIQU TMC5161 V1.0...........................................................................................648
    Links on SKR V1.4 TURBO Board...............................................................................648
    Links on SKR PRO V1.1 Board.................................................................................649
    Links on SKR PRO V1.2 Board.................................................................................650
    Links on SKR V1.3 Board.....................................................................................651
    Links on SKR V1.4 Board.....................................................................................652
    Links on GTR V1.0 Board.....................................................................................653
    Links on M5 V1.0 Add-on-board for GTR V1.0 Board............................................................654
    Miscellaneous Information...................................................................................655
    Miscellaneous Information (continued).......................................................................656
    Facebook Groups.............................................................................................662
APPENDIX G......................................................................................................663
  BIGTREETECH Reference Material for SKR PRO V1.1 Board.........................................................663
    SKR PRO V1.1 Original PIN Diagram...........................................................................663
    SKR PRO V1.1 Original Wiring Diagram 1......................................................................664
    SKR PRO V1.1 Original Wiring Diagram 2......................................................................665
    SKR PRO V1.1 Original PIN 1 Diagram.........................................................................666
    SKR PRO V1.1 Original Schematic Diagram.....................................................................667
APPENDIX H......................................................................................................668
  BIGTREETECH’s Smart Filament Sensor (SFS) Guide for SKR PRO V1.1 Board........................................668
  Information About BIGTREETECH’s SFS...........................................................................670
  SFS Wired to E0 Limit Switch or Endstop.......................................................................671
    Marlin 2.0.x Setup for SFS Connected to E0 Connector........................................................672
  Marlin 2.0.x Setup for SFS....................................................................................674
APPENDIX I......................................................................................................681
  “Connecting up Raspberry Pi via TFT Connector” Guide for SKR PRO V1.1 Board...................................681
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via TFT Connector..............................682
    TFT Connector Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable.............685
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................688
APPENDIX J......................................................................................................691
  “Connecting up Raspberry Pi via UART3 Header” Guide for SKR PRO V1.1 Board....................................691
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via UART3 Header...............................692
    UART3 Header Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable..............695
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................698
APPENDIX K......................................................................................................701
  “Connecting up Raspberry Pi via WIFI Header” Guide for SKR PRO V1.1 Board.....................................701
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via WIFI Header................................702
    WIFI Header Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable...............705
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................708
APPENDIX L......................................................................................................711
  BLTouch Guide for SKR PRO V1.1 Board..........................................................................711
  Connecting SKR PRO V1.1 with BLTouch..........................................................................712
    Wiring Diagram for Connecting SKR PRO V1.1 with BLTouch.....................................................715
  Marlin 2.0.x Firmware Setup for Connecting a BLTouch to SKR PRO V1.1 Board....................................716
    Explanation when to use Marlin variable Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN..................................721
    Understanding Marlin Firmware’s NOZZLE_TO_PROBE_OFFSET Setting..............................................725
APPENDIX M......................................................................................................740
  PT100 Sensor Connection Guide to the SKR PRO V1.1 Board via Analog ADC I/O Input..............................740
  Hyperlink Map for this PT100 Sensor Connection Guide via Analog ADC I/O Input.................................741
  Connecting  SKR PRO V1.1 with  PT100 Sensor...................................................................742
  E3D PT100 Amplifier Board Specifications......................................................................742
    E3D’s PT100 Amplifier Board -- Schematic Diagram............................................................743
    Hyperlink to Texas Instruments’ INA826  Amplifier Data Sheet................................................743
  Analog Procedure..............................................................................................746
    Connecting SKR PRO V1.1 Board with PT100 Amplifier Board and PT100 Sensor...................................746
      Locations of 3.3VDC Referenced to Analog Ground for the SKR PRO V1.1 Board’s Thermistor Ports.............757
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T1 (E0) Thermistor Port...........................759
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T2 (E1) Thermistor Port...........................761
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T3 (E2) Thermistor Port...........................763
    Instructions for Supplying Power to the PT100 Amplifier Board...............................................766
      Method #1 (5 VDC Digital PWR) for Powering the PT100 Amplifier Board for Techniques #1, and Technique #2..767
      Method #1 (3.3 VDC Digital PWR) for Powering the PT100 Amplifier Board 
        for Techniques #3, and Technique #4.....................................................................768
      Method #1 (5 VDC Digital PWR) for Powering the PT100 Amplifier Board 
        for Techniques #9,  Technique #10, Technique #11 and Technique #8.......................................769
      Method #1 (3.3 VDC Digital PWR) for Powering the PT100 Amplifier Board 
        for Techniques #5,  Technique #6, and Technique #7......................................................770
      Method #2 (3.3 VDC ref GNDA, Analog PWR) for Powering PT100 Amplifier Board 
        for Technique #5, Technique #6, and Technique #7........................................................771
    Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR).............................................772
    Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR).............................................773
    Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)...........................................774
    Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)...........................................775
    Wiring Diagram for Technique #5 & Method #1 (3.3 VDC Digital PWR)...........................................776
    Wiring Diagram for Technique #5 & Method #2 (3.3 VDC ref GNDA, Analog PWR)..................................777
    Wiring Diagram for Technique #6 & Method #1 (3.3 VDC Digital PWR)...........................................778
    Wiring Diagram for Technique #6 & Method #2 (3.3 VDC ref GNDA, Analog PWR)..................................779
    Wiring Diagram for Technique #7 & Method #1 (3.3 VDC Digital PWR)...........................................780
    Wiring Diagram for Technique #7 & Method #2 (3.3 VDC ref GNDA, Analog PWR)..................................781
    Wiring Diagram for Technique #8 & Method #1 (5 VDC Digital PWR).............................................782
    Wiring Diagram for Technique #9 & Method #1 (5 VDC Digital PWR).............................................783
    Wiring Diagram for Technique #10 & Method #1 (5 VDC Digital PWR)............................................784
    Wiring Diagram for Technique #11 & Method #1 (5 VDC Digital PWR)............................................785
    Marlin 2.0.x Firmware Setup for Connecting a PT100 Sensor to the SKR PRO V1.1 Board.........................786
      Marlin 2.0.x Firmware Setup for Technique #1..............................................................787
      Marlin 2.0.x Firmware Setup for Technique #2..............................................................794
      Marlin 2.0.x Firmware Setup for Technique #3..............................................................801
      Marlin 2.0.x Firmware Setup for Technique #4..............................................................808
      Marlin 2.0.x Firmware Setup for Technique #5..............................................................815
      Marlin 2.0.x Firmware Setup for Technique #6..............................................................822
      Marlin 2.0.x Firmware Setup for Technique #7..............................................................829
      Marlin 2.0.x Firmware Setup for Technique #8..............................................................836
      Marlin 2.0.x Firmware Setup for Technique #9..............................................................848
      Marlin 2.0.x Firmware Setup for Technique #10.............................................................855
      Marlin 2.0.x Firmware Setup for Technique #11.............................................................862
APPENDIX N......................................................................................................869
  PT100 Sensor Connection Guide to the SKR PRO V1.1 Board via Software SPI Protocol.............................869
  Hyperlink Map for this PT100 Sensor Connection Guide via Software SPI Protocol................................870
  Digital Procedure.............................................................................................871
    Connecting  SKR PRO V1.1 with Adafruit MAX31865 Board and PT100 Sensor......................................871
    Adafruit MAX31865 Board Specifications......................................................................872
      Adafruit MAX31865 Board -- Schematic Diagram..............................................................873
      Hyperlink to MAXIM Integrated’s MAX31865 Data Sheet.......................................................873
    Connecting SKR PRO V1.1 with MAX31865 Board via Software SPI................................................875
      Method #1 (5 VDC Digital PWR) for Powering the MAX31865 Board for Techniques #1,  and Technique #2........884
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31865 Board for Techniques #3,  and Technique #4......885
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)...........................................886
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)...........................................887
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR).........................................888
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR).........................................889
        Marlin 2.0.x Firmware Setup for Technique #1............................................................891
        Marlin 2.0.x Firmware Setup for Technique #2............................................................904
        Marlin 2.0.x Firmware Setup for Technique #3............................................................917
        Marlin 2.0.x Firmware Setup for Technique #4............................................................930
APPENDIX O......................................................................................................943
  PT100 Sensor Connection Guide to the SKR PRO V1.1 Board via Hardware SPI Protocol.............................943
  Hyperlink Map for this PT100 Sensor Connection Guide via Hardware SPI Protocol................................944
  Digital Procedure.............................................................................................945
    Connecting  SKR PRO V1.1 with Adafruit MAX31865 Board and PT100 Sensor......................................945
    Adafruit MAX31865 Board Specifications......................................................................946
      Adafruit MAX31865 Board -- Schematic Diagram..............................................................947
      Hyperlink to MAXIM Integrated’s MAX31865 Data Sheet.......................................................947
    Connecting  SKR PRO V1.1 with MAX31865 Board via Hardware SPI...............................................949
      Method #1 (5 VDC Digital PWR) for Powering the MAX31865 Board for Technique #1 and Technique #2...........959
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31865 Board for Technique #3 and Technique #4.........960
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)...........................................961
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)...........................................962
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR).........................................963
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR).........................................964
        Marlin 2.0.x Firmware Setup for Technique #1............................................................966
        Marlin 2.0.x Firmware Setup for Technique #2............................................................979
        Marlin 2.0.x Firmware Setup for Technique #3............................................................992
        Marlin 2.0.x Firmware Setup for Technique #4...........................................................1005
APPENDIX P.....................................................................................................1018
  K-Type Thermocouple Sensor Connection Guide to the SKR PRO V1.1 Board via Analog ADC I/O Input...............1018
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Analog ADC I/O Input..................1019
  Connecting  SKR PRO V1.1 with K-Type Thermocouple Sensor.....................................................1020
  Adafruit AD8495 Amplifier Board Specifications...............................................................1020
    Adafruit’s AD8495 Amplifier Board -- Schematic Diagram.....................................................1021
    Hyperlink to Analog Devices' AD8495 Amplifier Data Sheet...................................................1021
    How To Prevent a Noisy K-Type Thermocouple.................................................................1022
  Analog Procedure.............................................................................................1026
    Connecting SKR PRO V1.1 with K-Type Thermocouple Sensor and Adafruit’s AD8495 Amplifier Board..............1026
      Locations of 3.3VDC Referenced to Analog Ground for the SKR PRO V1.1 Board’s Thermistor Ports............1037
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T1 (E0) Thermistor Port..........................1039
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T2 (E1) Thermistor Port..........................1041
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T3 (E2) Thermistor Port..........................1043
    Instructions for Supplying Power to the AD8495 Amplifier Board.............................................1046
      Method #1 (5 VDC Digital PWR) for Powering the AD8495 Amplifier Board 
        for Techniques #1,  and Technique #2...................................................................1047
      Method #1 (3.3 VDC Digital PWR) for Powering the AD8495 Amplifier Board 
        for Techniques #3 and Technique #4.....................................................................1048
      Method #1 (5 VDC Digital PWR) for Powering the AD8495 Amplifier Board 
        for Techniques #9,  Technique #10, and Technique #11...................................................1049
      Method #1 (3.3 VDC Digital PWR) for Powering the AD8495 Amplifier Board 
        for Techniques #5,  Technique #6, Technique #7 and Technique #8........................................1050
      Method #2 (3.3 VDC ref GNDA, Analog PWR) for Powering AD8495 Amplifier Board 
        for Technique #5, Technique #6, and Technique #7.......................................................1051
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)..........................................1052
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)..........................................1053
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)........................................1054
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)........................................1055
      Wiring Diagram for Technique #5 & Method #1 (3.3 VDC Digital PWR)........................................1056
      Wiring Diagram for Technique #5 & Method #2 (3.3 VDC ref GNDA, Analog PWR)...............................1057
      Wiring Diagram for Technique #6 & Method #1 (3.3 VDC Digital PWR)........................................1058
      Wiring Diagram for Technique #6 & Method #2 (3.3 VDC ref GNDA, Analog PWR)...............................1059
      Wiring Diagram for Technique #7 & Method #1 (Digital PWR)................................................1060
      Wiring Diagram for Technique #7 & Method #2 (3.3 VDC ref GNDA, Analog PWR)...............................1061
      Wiring Diagram for Technique #8 & Method #1 (3.3 VDC Digital PWR)........................................1062
      Wiring Diagram for Technique #9 & Method #1 (5 VDC Digital PWR)..........................................1063
      Wiring Diagram for Technique #10 & Method #1 (5 VDC Digital PWR).........................................1064
      Wiring Diagram for Technique #11 & Method #1 (5 VDC Digital PWR).........................................1065
      Marlin 2.0.x Firmware Setup for Connecting a K-Type Thermocouple Sensor to the SKR PRO V1.1 Board........1066
        Marlin 2.0.x Firmware Setup for Technique #1...........................................................1067
        Marlin 2.0.x Firmware Setup for Technique #2...........................................................1075
        Marlin 2.0.x Firmware Setup for Technique #3...........................................................1083
        Marlin 2.0.x Firmware Setup for Technique #4...........................................................1091
        Marlin 2.0.x Firmware Setup for Technique #5...........................................................1099
        Marlin 2.0.x Firmware Setup for Technique #6...........................................................1107
        Marlin 2.0.x Firmware Setup for Technique #7...........................................................1115
        Marlin 2.0.x Firmware Setup for Technique #8...........................................................1123
        Marlin 2.0.x Firmware Setup for Technique #9...........................................................1138
        Marlin 2.0.x Firmware Setup for Technique #10..........................................................1146
        Marlin 2.0.x Firmware Setup for Technique #11..........................................................1154
APPENDIX Q.....................................................................................................1162
  K-Type Thermocouple Sensor Connection Guide to the SKR PRO V1.1 Board via Software SPI Protocol..............1162
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Software SPI Protocol.................1163
  Digital Procedure............................................................................................1164
    Connecting SKR PRO V1.1 with MAX31855 Amplifier Board and K-Type Thermocouple Sensor.......................1164
    MAX31855 Amplifier Board Specification.....................................................................1165
      Adafruit’s MAX31855 Amplifier Board -- Schematic Diagram.................................................1166
      Hyperlink to MAXIM’s MAX31855 Data Sheet.................................................................1166
      How To Prevent a Noisy K-Type Thermocouple...............................................................1167
    Connecting SKR PRO V1.1 with MAX31855 Amplifier Board via Software SPI.....................................1170
      Method #1 (5 VDC Digital PWR) for Powering the MAX31855 Amplifier Board 
        for Technique #1 and Technique #2......................................................................1177
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31855 Amplifier Board 
        for Technique #3 and Technique #4......................................................................1178
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)..........................................1179
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)..........................................1180
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)........................................1181
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)........................................1182
        Marlin 2.0.x Firmware Setup for Technique #1...........................................................1184
        Marlin 2.0.x Firmware Setup for Technique #2...........................................................1195
        Marlin 2.0.x Firmware Setup for Technique #3...........................................................1206
        Marlin 2.0.x Firmware Setup for Technique #4...........................................................1217
APPENDIX R.....................................................................................................1228
  K-Type Thermocouple Sensor Connection Guide to the SKR PRO V1.1 Board via Hardware SPI Protocol..............1228
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Hardware SPI Protocol.................1229
  Digital Procedure............................................................................................1230
    Connecting SKR PRO V1.1 with MAX31855 Amplifier Board and K-Type Thermocouple Sensor.......................1230
    MAX31855 Amplifier Board Specification.....................................................................1231
      Adafruit’s MAX31855 Amplifier Board -- Schematic Diagram.................................................1232
      Hyperlink to MAXIM’s MAX31855 Data Sheet.................................................................1232
      How To Prevent a Noisy K-Type Thermocouple...............................................................1233
    Connecting SKR PRO V1.1 with MAX31855 Amplifier Board via Hardware SPI.....................................1236
      Method #1 (5 VDC Digital PWR) for Powering the MAX31855 Amplifier Board 
         for Technique #1 and Technique #2.....................................................................1244
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31855 Amplifier Board 
         for Technique #3 and Technique #4.....................................................................1245
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)..........................................1246
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)..........................................1247
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)........................................1248
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)........................................1249
        Marlin 2.0.x Firmware Setup for Technique #1...........................................................1251
        Marlin 2.0.x Firmware Setup for Technique #2...........................................................1262
        Marlin 2.0.x Firmware Setup for Technique #3...........................................................1273
        Marlin 2.0.x Firmware Setup for Technique #4...........................................................1284
APPENDIX S.....................................................................................................1295
  EEPROM Guide for SKR PRO V1.1 Board..........................................................................1295
    Link to TWhite101 Instructable Guide called “BigTreeTech SKR Pro V1.1 or V1.2; Adding a EEPROM”............1296
Index..........................................................................................................1297
```
---

## Web Sites to Help ReCalibrate or Calibrate Your 3D Printer

https://teachingtechyt.github.io/calibration.html?fbclid=IwAR2HwowLZs4jnP0RU1pVZ1TmMxYbvNhqFvoGKGzCXAyCB_HdcZDkemmTJhc#intro

https://3dpc.nl/

---
