---
parent: Harmony 3 driver and system service application examples for PIC32CM JH01 family
title: FAT filesystem using SD-SPI driver
has_children: false
has_toc: false
---

[![MCHP](https://www.microchip.com/ResourcePackages/Microchip/assets/dist/images/logo.png)](https://www.microchip.com)

# FAT filesystem using SD-SPI driver

This application shows an example of using the MPLAB Harmony File System to access and modify the contents of a SD card using the SDSPI driver and the SPI PLIB.

## Description

### File System Operations on the SD Card:

- Application opens a file named FILE_TOO_LONG_NAME_EXAMPLE_123.JPG in the root directory of the SD card and reads its content into memory
- Application creates directory named Dir1 in the root directory
- Application creates a new file named FILE_TOO_LONG_NAME_EXAMPLE_123.JPG inside Dir1
- Application copies the content from step 1 into this newly created file

The reason for choosing a JPEG file for test purposes is that the duplicate file, Dir1/FILE_TOO_LONG_NAME_EXAMPLE_123.JPG created by the demonstration could be easily verified for correctness.If the new file inside Dir1 opens for viewing on the computer and matches to original image, the test is deemed to have passed. Otherwise, if the file does not open (i.e., is corrupted), the test will be considered to have failed.

Note:

*Since the application creates a directory named Dir1, it is important that the a folder with the same name does not exist on the SD card. If a directory named Dir1 is already present on the SD card, the application will fail.*

### File system layer uses:

- SDSPI Driver to communicate to SD Card over SPI interface.

## Downloading and building the application

To clone or download this application from Github, go to the [main page of this repository](https://github.com/Microchip-MPLAB-Harmony/core_apps_pic32cm_jh00_jh01) and then click Clone button to clone this repository or download as zip file.
This content can also be downloaded using content manager by following these [instructions](https://github.com/Microchip-MPLAB-Harmony/contentmanager/wiki).

Path of the application within the repository is **apps/fs/sdspi_fat/firmware** .

To build the application, refer to the following table and open the project using its IDE.

| Project Name      | Description                                    |
| ----------------- | ---------------------------------------------- |
| pic32cm_jh01_curiosity_pro.X | MPLABX project for [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/) |
|||

## Setting up the hardware

The following table shows the target hardware for the application projects.

| Project Name| Board|
|:---------|:---------:|
| pic32cm_jh01_curiosity_pro.X | [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/) |
|||



- To run the demo, the following additional hardware are required:
    - One micro-sd card
    - One [IO1 Xplained Pro Extension Kit](https://www.microchip.com/developmenttools/ProductDetails/ATIO1-XPRO)
    - Create a new JPEG file in the SD Card with name **FILE_TOO_LONG_NAME_EXAMPLE_123.JPG**

### Setting up [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/)

- Connect the Debug USB port on the board to the computer using a micro USB cable
- Connect [IO1 Xplained Pro Extension Kit](https://www.microchip.com/developmenttools/ProductDetails/ATIO1-XPRO) to the EXT1 header of [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/)
- Copy a JPEG file in the SD Card with name FILE_TOO_LONG_NAME_EXAMPLE_123.JPG
- Insert the micro-SD Card in the micro-SD Card slot of the [IO1 Xplained Pro Extension Kit](https://www.microchip.com/developmenttools/ProductDetails/ATIO1-XPRO)

## Running the Application

1. Build and program the application using its IDE
2. Press Switch to start the file operations
3. The LED is turned ON if there was no error during creating the directory and copying the file into it

Refer to the following table for switch and LED name:

| Board | Switch name | LED Name |
| ----- | -------- | --------- |
|  [PIC32CM JH01 Curiosity Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/) | SW0 | LED0 |
|||

4. If LED is ON, Insert the SD Card on to your host PC
5. SD Card should have the file **Dir1/FILE_TOO_LONG_NAME_EXAMPLE_123.JPG** and should match the original image
