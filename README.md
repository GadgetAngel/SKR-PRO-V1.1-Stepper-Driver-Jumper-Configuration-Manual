# SKR-PRO-V1.1-Stepper-Driver-Jumper-Configuration-Manual

:exclamation: This project provides documentation on how to configure stepper motor driver boards and
how to use them with the SKR PRO V1.1 3D printer controller board :exclamation:

## Table of Contents:

```
Stepper Driver Configurations for SKR PRO V1.1 Board
By       @GadgetAngel

POLOLU A4988.................................................................................................1
The (latest release of) Marlin Setup for POLOLU A4988 Drivers................................................5
BIQU A4988...................................................................................................9
The (latest release of) Marlin Setup for BIQU A4988 Drivers..................................................13
DRV8825......................................................................................................17
The (latest release of) Marlin Setup for DRV8825 Drivers.....................................................22
BIQU LV8729..................................................................................................27
The (latest release of) Marlin Setup for BIQU LV8729 Drivers.................................................32
FYSETC LV8729................................................................................................38
The (latest release of) Marlin Setup for FYSETC LV8729 Drivers...............................................43
LERDGE LV8729................................................................................................49
The (latest release of) Marlin Setup for LERDGE LV8729 Drivers...............................................54
MKS LV8729...................................................................................................60
The (latest release of) Marlin Setup for MKS LV8729 Drivers..................................................65
FYSETC S6128 V1.1............................................................................................71
The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers...........................................76
FYSETC ST820.................................................................................................82
The (latest release of) Marlin Setup for FYSETC ST820 Drivers................................................87
BIQU ST820...................................................................................................94
The (latest release of) Marlin Setup for BIQU ST820 Drivers..................................................99
POLOLU ST820 (STSPIN820).....................................................................................106
The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers....................................111
POLOLU MP6500................................................................................................118
The (latest release of) Marlin Setup for POLOLU MP6500 Drivers...............................................122
POLOLU TB67S249FTG...........................................................................................128
The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers..........................................133
BIQU S109....................................................................................................139
The (latest release of) Marlin Setup for BIQU S109 Drivers...................................................144
FYSETC S109..................................................................................................150
The (latest release of) Marlin Setup for FYSETC S109 Drivers.................................................155
BIQU TMC2100 Stand-alone Mode................................................................................161
The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode............................166
MKS TMC2100 Stand-alone Mode.................................................................................172
The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode.............................177
BIQU TMC2130 Stand-alone Mode................................................................................183
The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in Stand-alone Mode............................188
BIQU TMC2130 SPI Mode........................................................................................194
The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode....................................197
BIQU TMC2208 V3.0 Stand-alone Mode...........................................................................211
The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in Stand-alone Mode.......................215
BIQU TMC2208 V3.0 One Time Programming (OTP) Mode............................................................221
The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in One Time Programming (OTP) Mode........225
BIQU TMC2208 V3.0 UART Mode..................................................................................231
The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode..............................234
FYSETC TMC2208 V1.2 Stand-alone Mode.........................................................................245
The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in Stand-alone Mode.....................249
FYSETC TMC2208 V1.2 One Time Programming (OTP) Mode..........................................................255
The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in One Time Programming (OTP) Mode......259
FYSETC TMC2208 V1.2 UART Mode................................................................................265
The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode............................268
BIQU TMC2225 V1.0 Stand-alone Mode...........................................................................279
The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in Stand-alone Mode.......................283
BIQU TMC2225 V1.0 One Time Programming (OTP) Mode............................................................289
The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in One Time Programming (OTP) Mode........293
BIQU TMC2225 V1.0 UART Mode..................................................................................299
The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode..............................302
BIQU TMC2209 V1.2 Stand-alone Mode for StealthChop...........................................................313
The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for StealthChop.......317
BIQU TMC2209 V1.2 Stand-alone Mode for SpreadCycle...........................................................323
The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in Stand-alone Mode for SpreadCycle.......327
BIQU TMC2209 V1.2 UART Mode..................................................................................333
The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode..............................336
BIQU TMC5160 V1.2 SPI Mode...................................................................................350
The (latest release of) Marlin Setup for BIQU TMC5160 V1.2 Drivers in SPI Mode...............................353
BIQU TMC5161 V1.0 SPI Mode...................................................................................367
The (latest release of) Marlin Setup for BIQU TMC5161 V1.0 Drivers in SPI Mode...............................370
APPENDIX A...................................................................................................384
How to adjust the Vref on a Stepper Motor Driver board using the Potentiometer...............................384
APPENDIX B...................................................................................................386
For the TMC drivers what's the difference between stand-alone mode and ("UART" or "SPI ") modes?.............386
How to Calculate Vref for Non-TMC Stepper Motor Divers.......................................................386
How to Calculate Vref for TMC Stepper Motor Drivers..........................................................387
Driving Current Calculation Formulas for TMC Stepper Motor Drivers...........................................388
#1 TMC2100 with Rs=0.110? (110m?)............................................................................388
#2 TMC2130 with Rs=0.110? (110m?)............................................................................388
#3 TMC2208 with Rs=0.110? (110m?) for Stand-alone Mode.......................................................388
#4 TMC2208 with Rs=0.110? (110m?) for UART Mode..............................................................389
#5 TMC2209 with Rs=0.110? (110m?) for Stand-alone Mode.......................................................389
#6  TMC2209 with Rs=0.110? (110m?) for UART Mode.............................................................390
#7  TMC2225 with Rs=0.150? (150m?) for UART Mode.............................................................390
#8  TMC5160 with Rs=0.075? (75m?) for SPI Mode...............................................................390
#9  TMC5161 with Rs=0.062? (62m?) for SPI Mode...............................................................391
#10  TMC2225 with Rs=0.150? (150m?) for Stand-alone Mode.....................................................391
APPENDIX C...................................................................................................392
The (Latest Release of) Marlin Setup That Is Common To ALL Stepper Motor Drivers.............................392
SKR PRO V1.1 Color PINS Diagram..............................................................................405
SKR PRO V1.1 Color Wiring Diagram............................................................................406
```
