# RTOS-Based Embedded System on STM32

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/VThuong99/rtos-project)

## Overview
This project implements a Real-Time Operating System (RTOS) on an STM32 microcontroller, handling multiple real-time tasks such as LED control, EEPROM storage, and peripheral communication.

## Features
- **Multi-threading**: Uses FreeRTOS to manage multiple tasks efficiently.
- **EEPROM Storage**: Stores and retrieves data using internal EEPROM and external FRAM.
- **Peripheral Communication**: Interfaces with STM32 peripherals for data handling.
- **Task Scheduling**: Implements real-time task execution.

## Hardware Requirements
- **Microcontroller**: STM32F405rgtx
- **External Storage**: FRAM module 
- **Development Environment**: STM32CubeIDE

## Getting Started
### 1. Clone the repository
```sh
git clone https://github.com/VThuong99/rtos-project.git
cd rtos-project
```

### 2. Open in STM32CubeIDE
- Open STM32CubeIDE.
- Import the project (`File > Import > Existing Projects into Workspace`).

### 3. Build and Flash
- Connect the STM32 board via USB.
- Compile the code (`Project > Build Project`).
- Flash to STM32 (`Run > Run As > STM32 Cortex-M C/C++ Application`).

## Task Implementation
| Task  | Description |
|--------|--------------------------|
| Task 1 | Blinks an LED periodically |
| Task 2 | Saves internal temperature values to internal EEPROM |
| Task 3 | Reads temperature values from EEPROM and stores in external FRAM |

## Backup SRAM Usage Notes  
Since the STM32F405rgtx doesn't have internal EEPROM, Backup SRAM is used to simulate EEPROM. Key considerations include ensuring proper VBAT voltage, handling write protection, and managing the limited size. For detailed information on EEPROM emulation using Backup SRAM on STM32 MCUs, refer to the following application note:  
[AN4894: How to use EEPROM emulation on STM32 MCUs](http://st.com/resource/en/application_note/an4894-how-to-use-eeprom-emulation-on-stm32-mcus-stmicroelectronics.pdf)
