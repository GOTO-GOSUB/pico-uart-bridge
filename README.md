Raspberry Pi Pico USB-UART Bridge
=================================

This program bridges the Raspberry Pi Pico HW UARTs to two independent USB CDC serial devices in order to behave like any other USB-to-UART Bridge controllers. It has been modified from the source in order to make both UART's available on RP2040-Zero boards (the original conflicted UART0 with the WS2812 Neo Pixel LED) and still be compatible with the traditional Pico board.

Disclaimer
----------

This software is provided without warranty, according to the MIT License, and should therefore not be used where it may endanger life, financial stakes, or cause discomfort and inconvenience to others.

Raspberry Pi Pico Pinout
------------------------

| Raspberry Pi Pico GPIO | Function |
|:----------------------:|:--------:|
| GPIO12 (Pin 16)        | UART0 TX |
| GPIO13 (Pin 17)        | UART0 RX |
| GPIO4 (Pin 6)          | UART1 TX |
| GPIO5 (Pin 7)          | UART1 RX |

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
