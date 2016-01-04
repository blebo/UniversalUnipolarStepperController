# Universal Unipolar Stepper Controller

![board](https://raw.githubusercontent.com/IRNAS/UniversalUnipolarStepperController/master/StepperDriverV2.jpg)

![board](https://raw.githubusercontent.com/IRNAS/UniversalUnipolarStepperController/master/unipolar_connections_sch.png)

The lack of a low-cost stepper controller designed for use with the low-cost motors has motivated us to implement an universal solution with minor optimizations for use in KORUZA. Standalone unipolar motor driver has a number of welcome features:

 * driving 3 unipolar stepper motors 28BYJ48 or 24BYJ48 with suitable JST connectors
 * support for 6 end-switches, two which can be directly attached to the PCB without cables, such that control board can be positioned in a corner of the moving object.
 * support for 3 encoders for closed-loop control in high-precision systems
 * based on Texas Instruments MSP430G2955 in [Energia](http://energia.nu) environment
 * UART, I2C and SPI interfaces for receiving the control commands
 * unified serial connector for all interfaces
 * STATUS: operational prototype
 
Micro-controller has been chosen based on cost and pin number as well as availability in a sufficiently friendly package, however increasing the software development effort. Current revision has been tested with custom Energia code, however we aim to port to it [GRBL](https://github.com/grbl/grbl) firmware and thus make it directly interfacable from computer.

Alternative applications discovered thus-far for the controller board are listed below. We are always looking for ideas and people who would like to use it in their system, do get in touch:

 * 3D printer auto bed-levelling system
 * open-source microscope automation system
 * optics lab micrometer drive motorization
 * mini 3D printers and robots
 
## Firmware

Developed in Energia environment using MSP430G2955 microcontroller not yet officially supported, thus a bit more work in setting up the build environment. Currently only basic functions work and the firmware implemented is here KORUZA specific, but useful for other projects. GRBL port should happen in the future.

### Communicating with the board

UART communication at 115200 baud. Using EasyTransfer you send the whole data structure to the controller and change next values for where you would like the motors to move. Immediately the controller will reply with the data structure filled out with what next position it is moving to and current position where it is at. Positioning is absolute.

---

#### License

All our projects are as usefully open-source as possible.

Hardware including documentation is licensed under [CERN OHL v.1.2. license](http://www.ohwr.org/licenses/cern-ohl/v1.2)

Firmware and software originating from the project is licensed under [GNU GENERAL PUBLIC LICENSE v3](http://www.gnu.org/licenses/gpl-3.0.en.html).

Open data generated by our projects is licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/legalcode).

All our websites and additional documentation are licensed under [Creative Commons Attribution-ShareAlike 4 .0 Unported License] (https://creativecommons.org/licenses/by-sa/4.0/legalcode).

What this means is that you can use hardware, firmware, software and documentation without paying a royalty and knowing that you'll be able to use your version forever. You are also free to make changes but if you share these changes then you have to do so on the same conditions that you enjoy.

Koruza, GoodEnoughCNC and IRNAS are all names and marks of Institut IRNAS Rače. 
You may use these names and terms only to attribute the appropriate entity as required by the Open Licences referred to above. You may not use them in any other way and in particular you may not use them to imply endorsement or authorization of any hardware that you design, make or sell.
