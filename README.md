Serial Peripheral Interface (SPI) Protocol Design
Project Overview:
The Serial Peripheral Interface (SPI) is a widely used synchronous serial communication protocol that enables fast data transfer between microcontrollers and peripheral devices like sensors, memory chips, and ADCs. This project focuses on designing a customizable SPI core for embedded systems, ensuring efficient communication between a master and multiple slave devices.

Key Features:
Custom SPI Core Design: Implemented a flexible SPI controller with configurable clock speed and data transfer modes.
Master-Slave Communication: Supports full-duplex communication between the master and slave devices.
Clock and Data Synchronization: Designed with precise timing mechanisms to maintain data integrity.
Mode Selection: Supports all four SPI modes (Mode 0, 1, 2, 3) based on clock polarity and phase.
FPGA Implementation: Verified functionality using Xilinx Vivado tools on FPGA hardware.
Low Power & High-Speed Data Transfer: Optimized for embedded applications requiring real-time data exchange.
Technologies Used:
Hardware Description Language (HDL): Verilog / VHDL
Development Tools: Xilinx Vivado, ModelSim
Embedded Systems: FPGA, Microcontrollers
Applications:
Industrial Automation
IoT Devices
Memory Interfacing (EEPROM, Flash)
Sensor Data Acquisition
