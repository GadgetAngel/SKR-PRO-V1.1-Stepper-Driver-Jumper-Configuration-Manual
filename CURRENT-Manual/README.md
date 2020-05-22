# SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual

:exclamation: This project provides documentation on how to configure stepper motor driver boards and
how to use them with the SKR PRO V1.1 3D printer controller board :exclamation:
```
 I use Git for Windows with VScode to manage this repository.  I also use Git LFS extenstion for .pdf and .png files.

 Install Git with LFS extensions: https://git-lfs.github.com/

To Download the whole repository do the following: select the "Clone or download button" and click on "paste to clipboard" button so you can place the URL for the GitHub repository to the clipboard. Now Open Git Bash.
Change the current working directory to the location where you want the cloned directory.
Type git clone, and then paste the URL you copied earlier.
$ git clone https://github.com/GadgetAngel/SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual.git
Press Enter to create your local clone.
Now open Window explorer to the location of local clone.
```
The Repository now contains a .zip file that contains the whole repository. So, one can just hit one button to download the whole repository.  Just hit the "Download" button on the .zip file itself. If you see "view raw file" you can also mouse right click on the "view raw file" and  select "save link as.." from the pop up menu to save the .zip file to you local drive.

Also, You can download the .zip from my google drive located here:

## The Whole Repository in .zip file is located on Google Drive at https://drive.google.com/open?id=1ynmA4rw3QM6oHC4VUYeIZJsgLPiWB8C3

## Table of Contents:

```
Stepper Driver Configurations for SKR PRO V1.1 Board
By       @GadgetAngel

POLOLU A4988......................................................................................................1
  Driver Chip Chart for POLOLU A4988..............................................................................1
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.......................................2
  The (latest release of) Marlin Setup for POLOLU A4988 Drivers...................................................6
BIQU A4988........................................................................................................8
  Driver Chip Chart for BIQU 4988.................................................................................8
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.......................................9
  The (latest release of) Marlin Setup for BIQU A4988 Drivers....................................................13
DRV8825..........................................................................................................15
  Driver Chip Chart for POLOLU DRV8825...........................................................................15
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................16
  The (latest release of) Marlin Setup for DRV8825 Drivers.......................................................21
BIQU LV8729......................................................................................................24
  Driver Chip Chart for BIQU LV8729..............................................................................24
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................25
  The (latest release of) Marlin Setup for BIQU LV8729 Drivers...................................................30
FYSETC LV8729....................................................................................................34
  Driver Chip Chart for FYSETC LV8729............................................................................34
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................35
  The (latest release of) Marlin Setup for FYSETC LV8729 Drivers.................................................40
LERDGE LV8729....................................................................................................44
  Driver Chip Chart for LERDGE LV8729............................................................................44
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................45
  The (latest release of) Marlin Setup for LERDGE LV8729 Drivers.................................................50
MKS LV8729.......................................................................................................54
  Driver Chip Chart for MKS LV8729...............................................................................54
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................55
  The (latest release of) Marlin Setup for MKS LV8729 Drivers....................................................60
FYSETC S6128 V1.1................................................................................................64
  Driver Chip Chart for FYSETC S6128.............................................................................64
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................65
  The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers.............................................70
FYSETC ST820.....................................................................................................74
  Driver Chip Chart for FYSETC ST820.............................................................................74
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................75
  The (latest release of) Marlin Setup for FYSETC ST820 Drivers..................................................80
BIQU ST820.......................................................................................................85
  Driver Chip Chart for BIQU ST820...............................................................................85
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................86
  The (latest release of) Marlin Setup for BIQU ST820 Drivers....................................................91
POLOLU ST820 (STSPIN820).........................................................................................96
  Driver Chip Chart for POLOLU ST820.............................................................................96
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................97
  The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers.....................................102
POLOLU MP6500...................................................................................................107
  Driver Chip Chart for POLOLU MP6500...........................................................................107
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................108
  The (latest release of) Marlin Setup for POLOLU MP6500 Drivers................................................112
POLOLU TB67S249FTG..............................................................................................116
  Driver Chip Chart for POLOLU TB67S249FTG......................................................................116
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................117
  The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers...........................................122
BIQU S109.......................................................................................................126
  Driver Chip Chart for BIQU S109...............................................................................126
  SKR PRO 1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers......................................127
  The (latest release of) Marlin Setup for BIQU S109 Drivers....................................................132
FYSETC S109.....................................................................................................136
  Driver Chip Chart for FYSETC S109.............................................................................136
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................137
  The (latest release of) Marlin Setup for FYSETC S109 Drivers..................................................142
BIQU TMC2100 Stand-alone Mode...................................................................................146
  Driver Chip Chart for BIQU TMC2100 in Stand-alone Mode........................................................146
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers........................................147
  The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode.............................153
MKS TMC2100 Stand-alone Mode....................................................................................157
  Driver Chip Chart for MKS TMC2100 in Stand-alone Mode.........................................................157
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers........................................158
  The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode..............................164
BIQU TMC2130 Stand-alone Mode...................................................................................168
  Driver Chip Chart for BIQU TMC2130 in Stand-alone Mode........................................................168
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers........................................169
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in Stand-alone Mode.............................175
BIQU TMC2130 SPI Mode...........................................................................................179
  Driver Chip Chart for BIQU TMC2130 in SPI Mode................................................................179
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode.....................................182
BIQU TMC2208 V3.0 Stand-alone Mode..............................................................................194
  Driver Chip Chart for BIQU TMC2208 in Stand-alone Mode........................................................194
  SKR PRO V1.1 LEGEND of Driver Chip for Binary State Stepper Drivers...........................................195
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in Stand-alone Mode........................199
BIQU TMC2208 V3.0 One Time Programming (OTP) Mode...............................................................203
  Driver Chip Chart for BIQU TMC2208 in OTP Mode................................................................203
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................204
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in One Time Programming (OTP) Mode.........208
BIQU TMC2208 V3.0 UART Mode.....................................................................................212
  Driver Chip Chart for BIQU TMC2208 in UART Mode...............................................................212
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode...............................215
FYSETC TMC2208 V1.2 Stand-alone Mode............................................................................224
  Driver Chip Chart for FYSETC TMC2208 in Stand-alone Mode......................................................224
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................225
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in Stand-alone Mode......................229
FYSETC TMC2208 V1.2 One Time Programming (OTP) Mode.............................................................233
  Driver Chip Chart for FYSETC TMC2208 in OTP Mode..............................................................233
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................234
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in One Time Programming (OTP) Mode.......238
FYSETC TMC2208 V1.2 UART Mode...................................................................................242
  Driver Chip Chart for FYSETC TMC2208 in UART Mode.............................................................242
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode.............................245
BIQU TMC2225 V1.0 Stand-alone Mode..............................................................................254
  Driver Chip Chart for BIQU TMC2225 in Stand-alone Mode........................................................254
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................255
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in Stand-alone Mode........................259
BIQU TMC2225 V1.0 One Time Programming (OTP) Mode...............................................................263
  Driver Chip Chart for BIQU TMC2225 in OTP Mode................................................................263
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................264
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in One Time Programming (OTP) Mode.........268
BIQU TMC2225 V1.0 UART Mode.....................................................................................272
  Driver Chip Chart for BIQU TMC2225 in UART Mode...............................................................272
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode...............................275
BIQU TMC2209 V1.2 Stand-alone Mode for StealthChop..............................................................284
  Driver Chip Chart for BIQU TMC2209 in Stand-alone Mode (StealthChop)..........................................284
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................285
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for StealthChop........289
BIQU TMC2209 V1.2 Stand-alone Mode for SpreadCycle..............................................................293
  Driver Chip Chart for BIQU TMC2209 in Stand-alone Mode (SpreadCycle)..........................................293
  SKR PRO V1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers.....................................294
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for SpreadCycle........298
BIQU TMC2209 V1.2 UART Mode.....................................................................................302
  Driver Chip Chart for BIQU TMC2209 in UART Mode...............................................................302
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode...............................305
BIQU TMC5160 V1.2 SPI Mode......................................................................................317
  Driver Chip Chart for BIQU TMC5160 in SPI Mode................................................................317
  The (latest release of) Marlin Setup for BIQU TMC5160 V1.2 Drivers in SPI Mode................................320
BIQU TMC5161 V1.0 SPI Mode......................................................................................332
  Driver Chip Chart for BIQU TMC5161 in SPI Mode................................................................332
  The (latest release of) Marlin Setup for BIQU TMC5161 V1.0 Drivers in SPI Mode................................335
APPENDIX A......................................................................................................347
  How to adjust the Vref on a Stepper Motor Driver board using the Potentiometer................................347
APPENDIX B......................................................................................................349
  For the TMC drivers what's the difference between stand-alone mode and ("UART" or "SPI ") modes?..............349
  How to Calculate Vref for Non-TMC Stepper Motor Divers........................................................349
  How to Calculate Vref for TMC Stepper Motor Drivers...........................................................350
  Driving Current Calculation Formulas for TMC Stepper Motor Drivers............................................351
    #1 TMC2100 with Rs = 0.110Ω (110mΩ).........................................................................351
    #2 TMC2130 with Rs = 0.110Ω (110mΩ).........................................................................351
    #3 TMC2208 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode....................................................351
    #4 TMC2208 with Rs = 0.110Ω (110mΩ) for UART Mode...........................................................352
    #5 TMC2209 with Rs = 0.110 (110m) for Stand-alone Mode...................................................352
    #6 TMC2209 with Rs = 0.110Ω (110mΩ) for UART Mode...........................................................353
    #7 TMC2225 with Rs = 0.150Ω (150mΩ) for UART Mode...........................................................353
    #8 TMC5160 with Rs = 0.075Ω (75mΩ) for SPI Mode.............................................................353
    #9 TMC5161 with Rs = 0.062Ω (62mΩ) for SPI Mode.............................................................354
    #10 TMC2225 with Rs = 0.150 (150m) for Stand-alone Mode..................................................354
APPENDIX C......................................................................................................355
  The (Latest Release of) Marlin Setup That Is Common to ALL Stepper Motor Drivers..............................355
    Link to BIGTREETECH SKR PRO V1.1 User Manual.pdf............................................................355
    Link to BIGTREETECH SKR PRO V1.1 Guide.pdf..................................................................355
    Link to Pronterface Software................................................................................356
    Link to How to Calibrate your 3D Printer....................................................................356
    SKR PRO V1.1 Color PIN Diagram..............................................................................368
    SKR PRO V1.1 Color Wiring Diagram...........................................................................369
    SKR PRO V1.1 Color PIN 1 Diagram............................................................................371
    SKR PRO V1.1 Color Schematic Diagram........................................................................372
    SKR PRO V1.1 Uncolored Schematic Diagram....................................................................373
APPENDIX D......................................................................................................374
  Legends for SKR PRO V1.1 Stepper Driver Socket Representations................................................374
    SKR PRO 1.1 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers...................375
    SKR PRO 1.1 LEGEND of Driver Chip Chart for Binary State Stepper Drivers....................................381
      Special Consideration of D Jumper for SKR PRO V1.1 Board..................................................382
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.....................383
    SKR PRO V1.1 LEGEND of Driver Chip Chart for Tri State Stepper Drivers......................................389
    SKR PRO V1.1 LEGEND of Driver Socket Representation for SPI Capable Stepper Motor Drivers...................391
    SKR PRO V1.1 LEGEND of Driver Socket Representation for UART Capable Stepper Motor Drivers..................392
    SKR PRO V1.1 LEGEND of Driver Socket Representation for Sensor-less Homing Capable Stepper Motor Drivers....393
  Examples for Stepper Driver Socket Representations............................................................394
    Example 1 (LV8729 Driver Board; Binary State Driver) for SKR PRO V1.1 Driver Socket Representation..........394
    Example 2 (A4988 Driver Board; Binary State Driver) for SKR PRO V1.1 Driver Socket Representation...........395
    Example 3 (TMC2130 Driver Board in Stand-alone Mode; Tri State Driver) for 
      SKR PRO V1.1 Driver Socket Representation.................................................................396
    Example 4 (TMC2208 UART Driver Board) for SKR PRO V1.1 Driver Socket Representation.........................397
    Example 5 (TMC5160 SPI Driver Board) for SKR PRO V1.1 Driver Socket Representation..........................398
APPENDIX E......................................................................................................399
  Location Of “firmware.bin” File from the Marlin Compilation for SKR PRO V1.1 Board............................399
APPENDIX F......................................................................................................402
  Links to Reference Material...................................................................................402
    Marlin Firmware Documentation...............................................................................402
    Information on Stepper Motor Drivers and Micro-stepping.....................................................402
    POLOLU A4988 and BIQU A4988.................................................................................403
    DRV8825.....................................................................................................403
    BIQU LV8729, FYSETC LV8729, LERDGE LV8729, and MKS LV8729...................................................404
    BIQU LV8729.................................................................................................404
    FYSETC LV8729...............................................................................................405
    LERDGE LV8729...............................................................................................405
    MKS LV8729..................................................................................................406
    FYSETC S6128 V1.1...........................................................................................406
    FYSETC ST820................................................................................................407
    BIQU ST820..................................................................................................407
    POLOLU ST820 (STSPIN820)....................................................................................408
    POLOLU MP6500...............................................................................................408
    POLOLU TB67S249FTG..........................................................................................409
    BIQU S109 and FYSETC S109...................................................................................409
    BIQU S109...................................................................................................410
    FYSETC S109.................................................................................................410
    Marlin Firmware Documentation Specific to TMC Drivers.......................................................411
    Information Common to All TMC Drivers.......................................................................411
    BIQU TMC2100 and MKS TMC2100................................................................................412
    BIQU TMC2130................................................................................................413
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2.............................................413
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2 (Continued).................................414
    BIQU TMC2208 V3.0...........................................................................................414
    FYSETC TMC2208 V1.2.........................................................................................414
    Information Common to TMC2208 and BIQU TMC2225..............................................................415
    BIQU TMC2225 V1.0...........................................................................................415
    BIQU TMC2209 V1.2...........................................................................................416
    BIQU TMC5160 V1.2...........................................................................................416
    BIQU TMC5161 V1.0...........................................................................................417
    SKR PRO V1.1 Board..........................................................................................417
    Facebook Groups.............................................................................................418
    Miscellaneous Information...................................................................................419
APPENDIX G......................................................................................................420
  BIGTREETECH Reference Material................................................................................420
    Original PIN Diagram........................................................................................420
    Original Wiring Diagram 1...................................................................................421
    Original Wiring Diagram 2...................................................................................422
    Original PIN 1 Diagram......................................................................................423
    Original Schematic Diagram..................................................................................424
```

