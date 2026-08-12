Raspberry Pi Pico USB-UART Bridge
=================================

This program bridges the Raspberry Pi Pico HW UARTs to two independent USB CDC serial devices in order to behave like any other USB-to-UART Bridge controller. It has been modified from the source in order to make both UART's available on the Waveshare RP2040-Zero board since the original would cause a conflict between UART0 and the WS2812 Neo Pixel LED. This change maintains compatibility with a traditional Raspberry Pi Pico board by making the changes to the pinout as shown below.

Disclaimer
----------

This software is provided without warranty, according to the MIT License, and should therefore not be used where it may endanger life, financial stakes, or cause discomfort and inconvenience to others.

Raspberry Pi Pico Pinout
------------------------

| Raspberry Pi Pico GPIO | RP2040-Zero    | Function |
|:----------------------:|:--------------:|:--------:|
| GP12 (Pin 16)          | GP12 (12)      | UART0 TX |
| GP13 (Pin 17)          | GP13 (13)      | UART0 RX |
| GP4  (Pin 6)           | GP4  (4)       | UART1 TX |
| GP5  (Pin 7)           | GP5  (5)       | UART1 RX |

Build for Raspberry Pi Pico / Pico 2
------------------------------------

Prerequisites:
- CMake
- ARM GCC toolchain (e.g. `arm-none-eabi-gcc`)
- Python 3

Build steps:
1. Initialize submodules if you haven't already:
   - `git submodule update --init --recursive`
2. Run the build script (defaults to Pico 1):
   - `./build.sh`

The `.uf2` output will be created at `build/uart_bridge.uf2`.

Board override:
- To build for Pico 2, set `PICO_BOARD`:
  - `PICO_BOARD=pico2 ./build.sh`
