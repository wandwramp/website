---
title: Installing the WRAMP environment
subTitle: WAND - WRAMP
---

## Installing the ToolChain

Whether you are running the simulator or physical boards you will need to install the toolchain, comprising of [`wasm`, `wlink`](https://github.com/wandwramp/toolchain/releases) and [`wcc`](https://github.com/wandwramp/wcc/releases). These can be obtained from the releases page of their respective repos or built from source. `wcc` expects to be installed in the same location as `wasm` and `wlink` or as long as they are accessible from PATH.

The releases are built for Ubuntu16.04, more information can be found in the respective repos.

## Using the Simulator

The simulator ([`wsim`](https://github.com/wandwramp/wsim/releases)) runs under mono (tested with 4.2.1). Can also be obtained from releases or built from source.

## Using the physical boards

The [WRAMPsys](https://github.com/wandwramp/WRAMPsys) implementation was built for the [Basys3](https://reference.digilentinc.com/reference/programmable-logic/basys-3/start?redirect=1) FPGAs, meaning you will need Vivado and either a physical Basys3 board or modify the constraints file and rebuild the source for your particular FPGA yourself. The bitstream can be obtained from the releases section of the WRAMPsys (TODO: make a release for WRAMPsys) repo and instructions for flashing the boards can be found [here](https://reference.digilentinc.com/learn/programmable-logic/tutorials/basys-3-programming-guide/start#programming_the_basys3_using_quad_spi).

To interface with the board, you will need a serial connection, the Basys3 uses serial over the micro USB used to provide power. [Remote]() is provided as a convenient way to upload files to the board. The serial address of the board will need to be provided to remote, details are in the README. The default settings for this connection are a baud rate of 38400, one stop bit and no parity bits.

The physical boards also use an external serial connection for serial port 2 in the form of a [PMOD adapter](https://reference.digilentinc.com/reference/pmod/pmodusbuart/start?_ga=2.164554047.1466222969.1551922883-964591917.1510608463). This is plugged into the top left PMOD port on the Basys3 (the lower row).

## Interacting with the board

Whether you are using the physical board or the simulator upon restarting WRAMP you will be greeted by WRAMPmon via serial port 1  with the following display: 
```
+------------------------------------------------+
|                 WRAMPmon 0.7                   |
| Copyright 2002, 2003 The University of Waikato |
|                                                |
|          Written by Dean Armstrong             |
|       Ported to the Basys3 in 2018 by          |
|     Daniel Oosterwijk and Tyler Marriner       |
+------------------------------------------------+

Type ? and press enter for available commands.

 >
```
This is the command prompt for WRAMPmon. Using the `load` command, WRAMPmon will accept a file in `srec` format which can be built using `wlink`, files can be uploaded by following the prompt. See the manual for more information on writing WRAMP assembly and creating `srec` files.