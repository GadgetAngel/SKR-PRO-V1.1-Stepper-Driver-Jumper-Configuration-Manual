# SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual

:exclamation: This project provides documentation on how to configure stepper motor driver boards and
how to use them with the SKR PRO V1.1 3D printer controller board :exclamation:

## Table of Contents:

```
Stepper Driver Configurations for SKR PRO V1.1 Board
By       @GadgetAngel

POLOLU A4988.................................................................................................1
  The (latest release of) Marlin Setup for POLOLU A4988 Drivers..............................................6
BIQU A4988...................................................................................................8
  The (latest release of) Marlin Setup for BIQU A4988 Drivers...............................................13
DRV8825.....................................................................................................15
  The (latest release of) Marlin Setup for DRV8825 Drivers..................................................21
BIQU LV8729.................................................................................................24
  The (latest release of) Marlin Setup for BIQU LV8729 Drivers..............................................30
FYSETC LV8729...............................................................................................34
  The (latest release of) Marlin Setup for FYSETC LV8729 Drivers............................................40
LERDGE LV8729...............................................................................................44
  The (latest release of) Marlin Setup for LERDGE LV8729 Drivers............................................50
MKS LV8729..................................................................................................54
  The (latest release of) Marlin Setup for MKS LV8729 Drivers...............................................60
FYSETC S6128 V1.1...........................................................................................64
  The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers........................................70
FYSETC ST820................................................................................................74
  The (latest release of) Marlin Setup for FYSETC ST820 Drivers.............................................80
BIQU ST820..................................................................................................85
  The (latest release of) Marlin Setup for BIQU ST820 Drivers...............................................91
POLOLU ST820 (STSPIN820)....................................................................................96
  The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers................................102
POLOLU MP6500..............................................................................................107
  The (latest release of) Marlin Setup for POLOLU MP6500 Drivers...........................................112
POLOLU TB67S249FTG.........................................................................................116
  The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers......................................122
BIQU S109..................................................................................................126
  The (latest release of) Marlin Setup for BIQU S109 Drivers...............................................132
FYSETC S109................................................................................................136
  The (latest release of) Marlin Setup for FYSETC S109 Drivers.............................................142
BIQU TMC2100 Stand-alone Mode..............................................................................146
  The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode........................153
MKS TMC2100 Stand-alone Mode...............................................................................157
  The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode.........................164
BIQU TMC2130 Stand-alone Mode..............................................................................168
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in Stand-alone Mode........................175
BIQU TMC2130 SPI Mode......................................................................................179
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode................................182
BIQU TMC2208 V3.0 Stand-alone Mode.........................................................................194
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in Stand-alone Mode...................199
BIQU TMC2208 V3.0 One Time Programming (OTP) Mode..........................................................203
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in One Time Programming (OTP) Mode....208
BIQU TMC2208 V3.0 UART Mode................................................................................212
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode..........................215
FYSETC TMC2208 V1.2 Stand-alone Mode.......................................................................224
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in Stand-alone Mode.................229
FYSETC TMC2208 V1.2 One Time Programming (OTP) Mode........................................................233
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in One Time Programming (OTP) Mode..238
FYSETC TMC2208 V1.2 UART Mode..............................................................................242
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode........................245
BIQU TMC2225 V1.0 Stand-alone Mode.........................................................................254
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in Stand-alone Mode...................259
BIQU TMC2225 V1.0 One Time Programming (OTP) Mode..........................................................263
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in One Time Programming (OTP) Mode....268
BIQU TMC2225 V1.0 UART Mode................................................................................272
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode..........................275
BIQU TMC2209 V1.2 Stand-alone Mode for StealthChop.........................................................284
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for StealthChop...289
BIQU TMC2209 V1.2 Stand-alone Mode for SpreadCycle.........................................................293
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for SpreadCycle...298
BIQU TMC2209 V1.2 UART Mode................................................................................302
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode..........................305
BIQU TMC5160 V1.2 SPI Mode.................................................................................317
  The (latest release of) Marlin Setup for BIQU TMC5160 V1.2 Drivers in SPI Mode...........................320
BIQU TMC5161 V1.0 SPI Mode.................................................................................332
  The (latest release of) Marlin Setup for BIQU TMC5161 V1.0 Drivers in SPI Mode...........................335
APPENDIX A.................................................................................................347
  How to adjust the Vref on a Stepper Motor Driver board using the Potentiometer...........................347
APPENDIX B.................................................................................................349
  For the TMC drivers what's the difference between stand-alone mode and ("UART" or "SPI ") modes?.........349
  How to Calculate Vref for Non-TMC Stepper Motor Divers...................................................349
  How to Calculate Vref for TMC Stepper Motor Drivers......................................................350
  Driving Current Calculation Formulas for TMC Stepper Motor Drivers.......................................351
    #1 TMC2100 with Rs = 0.110Ω (110mΩ)....................................................................351
    #2 TMC2130 with Rs = 0.110Ω (110mΩ)....................................................................351
    #3 TMC2208 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode...............................................351
    #4 TMC2208 with Rs = 0.110Ω (110mΩ) for UART Mode......................................................352
    #5 TMC2209 with Rs = 0.110 (110m) for Stand-alone Mode..............................................352
    #6 TMC2209 with Rs = 0.110Ω (110mΩ) for UART Mode......................................................353
    #7 TMC2225 with Rs = 0.150Ω (150mΩ) for UART Mode......................................................353
    #8 TMC5160 with Rs = 0.075Ω (75mΩ) for SPI Mode........................................................353
    #9 TMC5161 with Rs = 0.062Ω (62mΩ) for SPI Mode........................................................354
    #10 TMC2225 with Rs = 0.150 (150m) for Stand-alone Mode.............................................354
APPENDIX C.................................................................................................355
  The (Latest Release of) Marlin Setup That Is Common to ALL Stepper Motor Drivers.........................355
    Link to BIGTREETECH SKR PRO V1.1 User Manual.pdf.......................................................355
    Link to BIGTREETECH SKR PRO V1.1 Guide.pdf.............................................................355
    Link to Pronterface Software...........................................................................356
    Link to How to Calibrate your 3D Printer...............................................................356
    SKR PRO V1.1 Color PIN Diagram.........................................................................368
    SKR PRO V1.1 Color Wiring Diagram......................................................................369
    SKR PRO V1.1 Color PIN 1 Diagram.......................................................................371
    SKR PRO V1.1 Color Schematic Diagram...................................................................372
APPENDIX D.................................................................................................373
  Legends for SKR PRO V1.1 Stepper Driver Socket Representations...........................................373
  Special Consideration of D Jumper for SKR PRO V1.1 Board.................................................376
  Examples for Stepper Driver Socket Representations.......................................................377
    Example 1 (LV8729 Driver Board) for SKR PRO V1.1 Driver Socket Legend..................................377
    Example 2 (A4988 Driver Board) for SKR PRO V1.1 Driver Socket Legend...................................378
    Example 3 (UART Driver Board) for SKR PRO V1.1 Driver Socket Legend....................................379
    Example 4 (SPI Driver Board) for SKR PRO V1.1 Driver Socket Legend.....................................380
APPENDIX E.................................................................................................381
  Location Of “firmware.bin” File from the Marlin Compilation for SKR PRO V1.1 Board.......................381
APPENDIX F.................................................................................................384
  Links to Reference Material..............................................................................384
    Marlin Firmware Documentation..........................................................................384
    Information on Stepper Motor Drivers and Micro-stepping................................................384
    POLOLU A4988 and BIQU A4988............................................................................385
    DRV8825................................................................................................385
    BIQU LV8729, FYSETC LV8729, LERDGE LV8729, and MKS LV8729..............................................386
    BIQU LV8729............................................................................................386
    FYSETC LV8729..........................................................................................387
    LERDGE LV8729..........................................................................................387
    MKS LV8729.............................................................................................388
    FYSETC S6128 V1.1......................................................................................388
    FYSETC ST820...........................................................................................389
    BIQU ST820.............................................................................................389
    POLOLU ST820 (STSPIN820)...............................................................................390
    POLOLU MP6500..........................................................................................390
    POLOLU TB67S249FTG.....................................................................................391
    BIQU S109 and FYSETC S109..............................................................................391
    BIQU S109..............................................................................................392
    FYSETC S109............................................................................................392
    Marlin Firmware Documentation Specific to TMC Drivers..................................................393
    Information Common to All TMC Drivers..................................................................393
    BIQU TMC2100 and MKS TMC2100...........................................................................394
    BIQU TMC2130...........................................................................................395
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2........................................395
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2 (Continued)............................396
    BIQU TMC2208 V3.0......................................................................................396
    FYSETC TMC2208 V1.2....................................................................................396
    Information Common to TMC2208 and BIQU TMC2225.........................................................397
    BIQU TMC2225 V1.0......................................................................................397
    BIQU TMC2209 V1.2......................................................................................398
    BIQU TMC5160 V1.2......................................................................................398
    BIQU TMC5161 V1.0......................................................................................399
    SKR PRO V1.1 Board.....................................................................................399
    Facebook Groups........................................................................................400
    Miscellaneous Information..............................................................................401
APPENDIX G.................................................................................................402
  BIGTREETECH Reference Material...........................................................................402
    Original PIN Diagram...................................................................................402
    Original Wiring Diagram 1..............................................................................403
    Original Wiring Diagram 2..............................................................................404
    Original PIN 1 Diagram.................................................................................405
    Original Schematic Diagram.............................................................................406
```

