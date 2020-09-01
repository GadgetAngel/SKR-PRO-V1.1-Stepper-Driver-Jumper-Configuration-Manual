# SKR-PRO-V1.1-Stepper-Driver-Jumper-Configurations-Manual

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
https://drive.google.com/file/d/1-K_8e5X_siQRn9Irg6GANT6iiXQq-ANt/view?usp=sharing    

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
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board..........................................8
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have 
      RST&SLP Set................................................................................................10
  The (latest release of) Marlin Setup for POLOLU A4988 Drivers..................................................15
BIQU A4988.......................................................................................................17
  Driver Chip Chart for BIQU A4988...............................................................................17
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........18
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................19
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have 
      RST&SLP Set................................................................................................21
  The (latest release of) Marlin Setup for BIQU A4988 Drivers....................................................26
DRV8825..........................................................................................................28
  Driver Chip Chart for DRV8825..................................................................................28
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........29
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................30
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have 
      RST&SLP Set................................................................................................32
  The (latest release of) Marlin Setup for DRV8825 Drivers.......................................................38
BIQU LV8729......................................................................................................41
  Driver Chip Chart for BIQU LV8729..............................................................................41
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...42
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
      RST&SLP Set................................................................................................44
  The (latest release of) Marlin Setup for BIQU LV8729 Drivers...................................................50
FYSETC LV8729....................................................................................................54
  Driver Chip Chart for FYSETC LV8729............................................................................54
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...55
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
      RST&SLP Set................................................................................................57
  The (latest release of) Marlin Setup for FYSETC LV8729 Drivers.................................................63
LERDGE LV8729....................................................................................................67
  Driver Chip Chart for LERDGE LV8729............................................................................67
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...68
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
      RST&SLP Set................................................................................................70
  The (latest release of) Marlin Setup for LERDGE LV8729 Drivers.................................................76
MKS LV8729.......................................................................................................80
  Driver Chip Chart for MKS LV8729...............................................................................80
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set...81
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
      RST&SLP Set................................................................................................83
  The (latest release of) Marlin Setup for MKS LV8729 Drivers....................................................89
FYSETC S6128 V1.1................................................................................................93
  Driver Chip Chart for FYSETC S6128 V1.1........................................................................93
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..........94
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board.........................................95
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
      RST&SLP Set................................................................................................97
  The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers............................................103
FYSETC ST820....................................................................................................107
  Driver Chip Chart for FYSETC ST820............................................................................107
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........108
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................109
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
      RST&SLP Set...............................................................................................111
  The (latest release of) Marlin Setup for FYSETC ST820 Drivers.................................................117
BIQU ST820......................................................................................................122
  Driver Chip Chart for BIQU ST820..............................................................................122
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........123
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................124
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have 
      RST&SLP Set...............................................................................................126
  The (latest release of) Marlin Setup for BIQU ST820 Drivers...................................................132
POLOLU ST820 (STSPIN820)........................................................................................137
  Driver Chip Chart for POLOLU ST820 (STSPIN820)................................................................137
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.........138
    Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board........................................139
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have 
      RST&SLP Set...............................................................................................141
  The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers.....................................147
POLOLU MP6500...................................................................................................152
  Driver Chip Chart for POLOLU MP6500...........................................................................152
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..153
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
      RST&SLP Set...............................................................................................155
  The (latest release of) Marlin Setup for POLOLU MP6500 Drivers................................................159
POLOLU TB67S249FTG..............................................................................................163
  Driver Chip Chart for POLOLU TB67S249FTG......................................................................163
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..164
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
      RST&SLP Set...............................................................................................166
  The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers...........................................172
BIQU S109.......................................................................................................176
  Driver Chip Chart for BIQU S109...............................................................................176
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..177
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
      RST&SLP Set...............................................................................................179
  The (latest release of) Marlin Setup for BIQU S109 Drivers....................................................185
FYSETC S109.....................................................................................................189
  Driver Chip Chart for FYSETC S109.............................................................................189
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set..190
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
      RST&SLP Set...............................................................................................192
  The (latest release of) Marlin Setup for FYSETC S109 Drivers..................................................198
BIQU TMC2100 Stand-alone Mode...................................................................................202
  Driver Chip Chart for BIQU TMC2100 in Stand-alone Mode........................................................202
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 1................................203
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 2................................204
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................206
  The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode.............................211
MKS TMC2100 Stand-alone Mode....................................................................................215
  Driver Chip Chart for MKS TMC2100 in Stand-alone Mode.........................................................215
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 1................................216
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 2................................217
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................219
  The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode..............................224
BIQU TMC2130 (SA) Stand-alone Mode..............................................................................228
  Driver Chip Chart for BIQU TMC2130 (SA) in Stand-alone Mode...................................................228
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 1................................229
  SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers - PART 2................................230
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.......................232
BIQU TMC2130 SPI Mode...........................................................................................241
  Driver Chip Chart for BIQU TMC2130 in SPI Mode................................................................241
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.....................244
  Information on Sensor-less Homing for SKR PRO V1.1............................................................247
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode.....................................252
BIQU TMC2208 V3.0 (SA) Stand-alone Mode for StealthChop.........................................................266
  Driver Chip Chart for BIQU TMC2208 V3.0 (SA) in Stand-alone Mode (StealthChop)................................266
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (StealthChop)............................................................................267
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (StealthChop)............................................................................269
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (SA) Drivers in Stand-alone Mode for StealthChop...273
BIQU TMC2208 V3.0 (OTP) Stand-alone Mode for SpreadCycle........................................................277
  Driver Chip Chart for BIQU TMC2208 V3.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................277
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................278
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................280
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..284
BIQU TMC2208 V3.0 UARTMode......................................................................................288
  Driver Chip Chart for BIQU TMC2208 V3.0 in UART Mode..........................................................288
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................291
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode...............................297
FYSETC TMC2208 V1.2 (SA) Stand-alone Mode for StealthChop.......................................................306
  Driver Chip Chart for FYSETC TMC2208 V1.2 (SA) in Stand-alone Mode (StealthChop)..............................306
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (StealthChop)............................................................................307
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (StealthChop)............................................................................309
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop.313
FYSETC TMC2208 V1.2 (OTP) Stand-alone Mode for SpreadCycle......................................................317
  Driver Chip Chart for FYSETC TMC2208 V1.2 (OTP) in Stand-alone Mode (SpreadCycle).............................317
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................318
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................320
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (OTP) Drivers in 
      Stand-alone Mode for SpreadCycle..........................................................................324
FYSETC TMC2208 V1.2 UARTMode....................................................................................328
  Driver Chip Chart for FYSETC TMC2208 V1.2 in UART Mode........................................................328
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................331
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode.............................337
BIQU TMC2225 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................346
  Driver Chip Chart for BIQU TMC2225 V1.0 (SA) in Stand-alone Mode (StealthChop)............................... 346
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (StealthChop)............................................................................347
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (StealthChop)............................................................................349
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...353
BIQU TMC2225 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................357
  Driver Chip Chart for BIQU TMC2225 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................357
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................358
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................360
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..364
BIQU TMC2225 V1.0 UARTMode......................................................................................368
  Driver Chip Chart for BIQU TMC2225 V1.0 in UART Mode..........................................................368
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................371
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode...............................377
BIQU TMC2209 V1.2 (SA) Stand-alone Mode for StealthChop.........................................................386
  Driver Chip Chart for BIQU TMC2209 V1.2 (SA) in Stand-alone Mode (StealthChop)................................386
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (StealthChop)............................................................................387
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (StealthChop)............................................................................389
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop...393
BIQU TMC2209 V1.2 (OTP) Stand-alone Mode for SpreadCycle........................................................397
  Driver Chip Chart for BIQU TMC2209 V1.2 (OTP) in Stand-alone Mode (SpreadCycle)...............................397
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................398 
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................400
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (OTP) Drivers in Stand-alone Mode for SpreadCycle..404
BIQU TMC2209 V1.2 UARTMode......................................................................................408
  Driver Chip Chart for BIQU TMC2209 V1.2 in UART Mode..........................................................408
  SKR PRO V1.1 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode....................411
  Information on Sensor-less Homing for SKR PRO V1.1............................................................415
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode...............................420
BIQU TMC2226 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................434
  Driver Chip Chart for BIQU TMC2226 V1.0 (SA) in Stand-alone Mode (StealthChop)................................434
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (StealthChop)............................................................................435
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (StealthChop)............................................................................437
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...441
BIQU TMC2226 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................445
  Driver Chip Chart for BIQU TMC2226 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................445
  SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................446
  SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
      Stand-alone Mode (SpreadCycle)............................................................................448
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..452
BIQU TMC2226 V1.0 UARTMode......................................................................................456
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
    How to Tune Stepper Motor Drivers1..........................................................................532
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
      #6 TMC2209 with Rs = 0.110Ω (110mΩ) for UART Mode.........................................................539
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
    SKR PRO V1.1 Color PIN Diagram..............................................................................556
    SKR PRO V1.1 Color Wiring Diagram...........................................................................557
    SKR PRO V1.1 Color PIN 1 Diagram............................................................................559
    SKR PRO V1.1 Color Schematic Diagram........................................................................560
    SKR PRO V1.1 Uncolored Schematic Diagram....................................................................561
APPENDIX D......................................................................................................562
  Legends for SKR PRO V1.1 Stepper Driver Jumper Configurations.................................................562
  SKR PRO V1.1 LEGEND COMMON to ALL Driver Socket Representation................................................563
  SKR PRO V1.1 LEGENDS for Driver Socket Representations and LEGENDS for Driver Chip Charts.....................567
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
        RST&SLP Set.............................................................................................567
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.......570
      Special Consideration of “D” Jumper (RST&SLP) for SKR PRO V1.1 Board......................................571
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
        RST&SLP Set.............................................................................................572
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have 
        RST&SLP PINS Set........................................................................................575
    SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
        Stand-alone Mode (StealthChop)..........................................................................576
    SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
        Stand-alone Mode (StealthChop)..........................................................................578
    SKR PRO V1.1 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
        Stand-alone Mode (SpreadCycle)..........................................................................579
    SKR PRO V1.1 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in 
        Stand-alone Mode (SpreadCycle)..........................................................................581
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.....................582
    SKR PRO V1.1 LEGEND of Driver Chip Chart forTri State Stepper Drivers.......................................584
    SKR PRO V1.1 LEGEND of Driver Socket Representation for SPI Capable Stepper Motor Drivers...................585
    SKR PRO V1.1 LEGEND of Driver Socket Representation for UART Capable Stepper Motor Drivers..................592
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Sensor-less Homing Capable Stepper Motor Drivers....601
  SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations.................................................607
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for Binary State Drivers without RST&SLP Set..607
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for Binary State Drivers with RST&SLP Set.....611
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations forTri State Drivers..........................615
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2209 with Sensor-less Homing...........622
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2209 without Sensor-less Homing........623
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2130 with Sensor-less Homing...........624
    SKR PRO V1.1 Examples of Stepper Driver Jumper Configurations for TMC2130 without Sensor-less Homing........625
APPENDIX E......................................................................................................626
  Location Of “firmware bin” File from the Marlin Compilation for SKR PRO V1.1 Board............................626
APPENDIX F......................................................................................................629
  Links to Reference Material...................................................................................629
    Marlin Firmware Documentation...............................................................................629
    Information on Stepper Motor Drivers and Micro-stepping.....................................................629
    POLOLU A4988 and BIQU A4988.................................................................................630
    DRV8825.....................................................................................................630
    BIQU LV8729, FYSETC LV8729, LERDGE LV8729, and MKS LV879....................................................631
    BIQU LV8729.................................................................................................631
    FYSETC LV8729...............................................................................................632
    LERDGE LV8729...............................................................................................632
    MKS LV8729..................................................................................................633
    FYSETC S6128 V1.1...........................................................................................633
    FYSETC ST820................................................................................................634
    BIQU ST820..................................................................................................634
    POLOLU ST820 (STSPIN820)....................................................................................635
    POLOLU MP6500...............................................................................................635
    POLOLU TB67S249FTG..........................................................................................636
    BIQU S109 and FYSETC S109...................................................................................636
    BIQU S109...................................................................................................637
    FYSETC S109.................................................................................................637
    Marlin Firmware Documentation Specific to TMC Drivers.......................................................638
    Information Common to All TMC Drivers.......................................................................638
    BIQU TMC2100 and MKS TMC2100................................................................................639
    BIQU TMC2130................................................................................................640
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2.............................................640
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2 (Continued).................................641
    BIQU TMC2208 V3.0...........................................................................................641
    FYSETC TMC2208 V1.2.........................................................................................641
    Information Common to TMC2208 and BIQU TMC2225..............................................................642
    BIQU TMC2225 V1.0...........................................................................................642
    BIQU TMC2209 V1.2...........................................................................................643
    BIQU TMC5160 V1.2...........................................................................................643
    BIQU TMC5161 V1.0...........................................................................................644
    Links on SKR V1 4 TURBO Board...............................................................................644
    Links on SKR PRO V1.1 Board.................................................................................645
    Miscellaneous Information...................................................................................646
    Miscellaneous Information (continued).......................................................................647
    Facebook Groups.............................................................................................652
APPENDIX G......................................................................................................653
  BIGTREETECH Reference Material for SKR PRO V1.1 Board.........................................................653
    SKR PRO V1.1 Original PIN Diagram...........................................................................653
    SKR PRO V1.1 Original Wiring Diagram 1......................................................................654
    SKR PRO V1.1 Original Wiring Diagram 2......................................................................655
    SKR PRO V1.1 Original PIN 1 Diagram.........................................................................656
    SKR PRO V1.1 Original Schematic Diagram.....................................................................657
APPENDIX H......................................................................................................658
  BIGTREETECH’s Smart Filament Sensor (SFS) Guide for SKR PRO V1.1 Board........................................658
  Information About BIGTREETECH’s SFS...........................................................................660
  SFS Wired to Limit Switch{X-, Y-, Z-, E0, E1, or E2}..........................................................661
    Marlin 2.0.x Setup for SFS Connected to E0 Connector........................................................662
    Marlin 2.0.x Setup for SFS..................................................................................664
APPENDIX I......................................................................................................671
  “Connecting up Raspberry Pi via TFT Connector” Guide for SKR PRO V1.1 Board...................................671
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via TFT Connector..............................672
    TFT Connector Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable.............675
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................678
APPENDIX J......................................................................................................681
  “Connecting up Raspberry Pi via UART3 Header” Guide for SKR PRO V1.1 Board....................................681
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via UART3 Header...............................682
    UART3 Header Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable..............685
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................688
APPENDIX K......................................................................................................691
  “Connecting up Raspberry Pi via WIFI Header” Guide for SKR PRO V1.1 Board.....................................691
  Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable Via WIFI Header................................692
    WIFI Header Wiring Diagram for Connecting SKR PRO V1.1 to Raspberry Pi to Eliminate USB Cable...............695
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................698
APPENDIX L......................................................................................................701
  BLTouch Guide for SKR PRO V1.1 Board..........................................................................701
  Connecting SKR PRO V1.1 with BLTouch..........................................................................702
    Wiring Diagram for Connecting SKR PRO V1.1 with BLTouch.....................................................705
  Marlin 2.0.x Firmware Setup for Connecting a BLTouch to SKR PRO V1.1 Board....................................706
    Explanation when to use Marlin variable Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN..................................711
    Understanding Marlin Firmware’s NOZZLE_TO_PROBE_OFFSET Setting..............................................715
APPENDIX M......................................................................................................730
  PT100 Sensor Connection Guide to the SKR PRO V1.1 Board via Analog ADC I/O Input..............................730
  Hyperlink Map for this PT100 Sensor Connection Guide via Analog ADC I/O Input.................................731
  Connecting SKR PRO V1.1 Board with  PT100 Sensor..............................................................732
  Analog Procedure..............................................................................................734
    Connecting SKR PRO V1.1 Board with PT100 Amplifier Board and PT100 Sensor...................................734
      Locations of 3.3VDC Referenced to Analog Ground for the SKR PRO V1.1 Board’s Thermistor Ports.............743
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T1 (E0) Thermistor Port...........................745
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T2 (E1) Thermistor Port...........................747
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T3 (E2) Thermistor Port...........................749
    Instructions for Suppling Power to the PT100 Amplifier Board................................................752
      Method #1 for Powering the PT100 Amplifier Board (Digital PWR)............................................753
      Method #2 for Powering PT100 Amplifier Board (Analog PWR).................................................754
    Wiring Diagram forTechnique #1 & Method #1 (Digital PWR)....................................................755
    Wiring Diagram forTechnique #2 & Method #1 (Digital PWR)....................................................756
    Wiring Diagram forTechnique #3 & Method #1 (Digital PWR)....................................................757
    Wiring Diagram forTechnique #4 & Method #1 (Digital PWR)....................................................758
    Wiring Diagram forTechnique #5 & Method #1 (Digital PWR)....................................................759
    Wiring Diagram forTechnique #5 & Method #2 (Analog PWR).....................................................760
    Wiring Diagram forTechnique #6 & Method #1 (Digital PWR)....................................................761
    Wiring Diagram forTechnique #6 & Method #2 (Analog PWR).....................................................762
    Wiring Diagram forTechnique #7 & Method #1 (Digital PWR)....................................................763
    Wiring Diagram forTechnique #7 & Method #2 (Analog PWR).....................................................764
    Wiring Diagram forTechnique #8 & Method #1 (Digital PWR)....................................................765
    Marlin 2.0.x Firmware Setup for Connecting a PT100 Sensor to the SKR PRO V1.1 Board.........................766
      Marlin 2.0.x Firmware Setup forTechnique #1...............................................................767
      Marlin 2.0.x Firmware Setup forTechnique #2...............................................................772
      Marlin 2.0.x Firmware Setup forTechnique #3...............................................................777
      Marlin 2.0.x Firmware Setup forTechnique #4...............................................................782
      Marlin 2.0.x Firmware Setup forTechnique #5...............................................................787
      Marlin 2.0.x Firmware Setup forTechnique #6...............................................................792
      Marlin 2.0.x Firmware Setup forTechnique #7...............................................................797
      Marlin 2.0.x Firmware Setup forTechnique #8...............................................................802
APPENDIX N......................................................................................................814
  PT100 Sensor Connection Guide to the SKR PRO V1.1 Board via SPI Protocol (Software)...........................814
  Hyperlink Map for this PT100 Sensor Connection Guide via SPI Protocol (Software)..............................815
  Digital Procedure.............................................................................................816
    Connecting SKR PRO V1.1 with MAX31865 Amplifier Board and PT100 Sensor......................................816
      Connecting SKR PRO V1.1 with MAX31865 Amplifier Board via Software SPI....................................818
        Method #1 for Powering the MAX31865 Amplifier Board (Digital PWR).......................................827
        Wiring Diagram forTechnique #1 & Method #1 (Digital PWR)................................................828
        Wiring Diagram forTechnique #2 & Method #1 (Digital PWR)................................................829
        Wiring Diagram forTechnique #3 & Method #1 (Digital PWR)................................................830
        Wiring Diagram forTechnique #4 & Method #1 (Digital PWR)................................................831
        Marlin 2.0.x Firmware Setup forTechnique #1.............................................................833
        Marlin 2.0.x Firmware Setup forTechnique #2.............................................................840
        Marlin 2.0.x Firmware Setup forTechnique #3.............................................................847
        Marlin 2.0.x Firmware Setup forTechnique #4.............................................................854
APPENDIX O......................................................................................................861
  K-Type Thermocouple Sensor Connection Guide to the SKR PRO V1.1 Board via Analog ADC I/O Input................861
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Analog ADC I/O Input...................862
  Connecting SKR PRO V1.1 Board with K-Type Thermocouple Sensor.................................................863
  Analog Procedure..............................................................................................865
    Connecting SKR PRO V1.1 with K-Type Thermocouple Sensor and Adafruit’s AD8495 Amplifier Board...............865
      Locations of 3.3VDC Referenced to Analog Ground for the SKR PRO V1.1 Board’s Thermistor Ports.............874
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T1 (E0) Thermistor Port...........................876
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T2 (E1) Thermistor Port...........................878
      Hardware Hack Instructions for the SKR PRO V1.1 Board’s T3 (E2) Thermistor Port...........................880
    Instructions for Suppling Power to the AD8495 Amplifier Board...............................................883
      Method #1 for Powering the AD8495 Amplifier Board (Digital PWR)...........................................884
      Method #2 for Powering AD8495 Amplifier Board (Analog PWR)................................................885
    Wiring Diagram forTechnique #1 & Method #1 (Digital PWR)....................................................886
    Wiring Diagram forTechnique #2 & Method #1 (Digital PWR)....................................................887
    Wiring Diagram forTechnique #3 & Method #1 (Digital PWR)....................................................888
    Wiring Diagram forTechnique #4 & Method #1 (Digital PWR)....................................................889
    Wiring Diagram forTechnique #5 & Method #1 (Digital PWR)....................................................890
    Wiring Diagram forTechnique #5 & Method #2 (Analog PWR).....................................................891
    Wiring Diagram forTechnique #6 & Method #1 (Digital PWR)....................................................892
    Wiring Diagram forTechnique #6 & Method #2 (Analog PWR).....................................................893
    Wiring Diagram forTechnique #7 & Method #1 (Digital PWR)....................................................894
    Wiring Diagram forTechnique #7 & Method #2 (Analog PWR).....................................................895
    Wiring Diagram forTechnique #8 & Method #1 (Digital PWR)....................................................896
    Marlin 2.0.x Firmware Setup for Connecting a K-Type Thermocouple Sensor to the SKR PRO V1.1 Board...........897
      Marlin 2.0.x Firmware Setup forTechnique #1...............................................................898
      Marlin 2.0.x Firmware Setup forTechnique #2...............................................................904
      Marlin 2.0.x Firmware Setup forTechnique #3...............................................................910
      Marlin 2.0.x Firmware Setup forTechnique #4...............................................................916
      Marlin 2.0.x Firmware Setup forTechnique #5...............................................................922
      Marlin 2.0.x Firmware Setup forTechnique #6...............................................................928
      Marlin 2.0.x Firmware Setup forTechnique #7...............................................................934
      Marlin 2.0.x Firmware Setup forTechnique #8...............................................................940
APPENDIX P......................................................................................................955
  K-Type Thermocouple Sensor Connection Guide to the SKR PRO V1.1 Board via SPI Protocol (Software).............955
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via SPI Protocol (Software)................956
  Digital Procedure.............................................................................................957
    Connecting SKR PRO V1.1 with MAX31855 Amplifier Board and K-Type Thermocouple Sensor........................957
      Connecting SKR PRO V1.1 with MAX31855 Amplifier Board via Software SPI....................................959
        Method #1 for Powering the MAX31855 Amplifier Board (Digital PWR).......................................966
        Wiring Diagram forTechnique #1 & Method #1 (Digital PWR)................................................967
        Wiring Diagram forTechnique #2 & Method #1 (Digital PWR)................................................968
        Wiring Diagram forTechnique #3 & Method #1 (Digital PWR)................................................969
        Wiring Diagram forTechnique #4 & Method #1 (Digital PWR)................................................970
        Marlin 2.0.x Firmware Setup forTechnique #1.............................................................972
        Marlin 2.0.x Firmware Setup forTechnique #2.............................................................979
        Marlin 2.0.x Firmware Setup forTechnique #3.............................................................986
        Marlin 2.0.x Firmware Setup forTechnique #4.............................................................993
APPENDIX Q.....................................................................................................1000
  EEPROM Guide for SKR PRO V1.1 Board..........................................................................1000
    Link to TWhite101 Instructable Guide called “BigTreeTech SKR Pro V1.1 or V1.2; Adding a EEPROM”............1001
Index..........................................................................................................1002
```