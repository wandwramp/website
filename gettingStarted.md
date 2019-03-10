---
title: Installing the WRAMP envirment
subTitle: WAND - WRAMP
---

## Installing the ToolChain

Weather you are running the simulator or physical boards you will need to install the toolcahin, compruising of [`wasm`, `wlink`](https://github.com/wandwramp/toolchain/releases) and [`wcc`](https://github.com/wandwramp/wcc/releases). These can be obtained from the releases page of their respective repos or built from source. `wcc` expects to be installed in the same location as `wasm` and `wlink` or as long as they are accesaible from PATH.

The releases are built for Ubuntu16.04, more information can be found in the respective repos.

## Using the Simulator

The simulator ([`wsim`](https://github.com/wandwramp/wsim/releases)) runs under mono (tested with 4.2.1). Can also be obtainded from releases or built from source.

## Using the physical boards

The [WRAMPsys](https://github.com/wandwramp/WRAMPsys) implimentation was built for the [Basys3](https://reference.digilentinc.com/reference/programmable-logic/basys-3/start?redirect=1) FPGAs, meaning you will need Vivado and either a physical Basys3 board, or modify the constraints file and rebuild the source for your particular FPGA yourself. The bitstream can be obtained from the releases section of the WRAMPsys (TODO: make release for WRAMPsys) repo and instructions for flashing the boards can be found [here](https://reference.digilentinc.com/learn/programmable-logic/tutorials/basys-3-programming-guide/start#programming_the_basys3_using_quad_spi).

They physical boards also use an external serial connection in the form of a [PMOD adapter](https://reference.digilentinc.com/reference/pmod/pmodusbuart/start?_ga=2.164554047.1466222969.1551922883-964591917.1510608463). This is plugged into the top right PMOD port on the Basys3 (the lower row). 

To interface with the board you will need a serial connection, the Basys3 uses serial over the micro USB used to provide power. [Remote]() is provided as a convienient way to upload files to the board. The serial address of the board will need to be provided to remote, details are in the README.