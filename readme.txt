/**
  @page BLE_Scanner Application

  @verbatim
  ******************************************************************************
  * @file    BLE/BLE_Scanner/readme.txt 
  * @author  MCD Application Team
  * @brief   Description of the BLE_p2pClient application
  ******************************************************************************
  *
  * Copyright (c) 2020 STMicroelectronics. All rights reserved.
  *
  * This software component is licensed by ST under Ultimate Liberty license 
  * SLA0044, the "License"; You may not use this file except in compliance with 
  * the License. You may obtain a copy of the License at:
  *                               www.st.com/SLA0044
  *
  ******************************************************************************
  @endverbatim

@par Application Description

This example is to demonstrate a connectable scanner using BLE component. 

Repertory : STM32CubeWB\Projects\P-NUCLEO-WB55.Nucleo\Applications\BLE\BLE_Scanner

A STM32WB55xx boards is used, acting as GAP Central & GATT client.
This Application works with the 1.9 release.


@par Keywords

Connectivity, BLE, IPCC, HSEM, RTC, UART, PWR, BLE protocol, BLE pairing, BLE profile, Dual core

@par Directory contents 
  
  - BLE/BLE_Scanner/Core/Inc/stm32wbxx_hal_conf.h		HAL configuration file
  - BLE/BLE_Scanner/Core/Inc/stm32wbxx_it.h          	Interrupt handlers header file
  - BLE/BLE_Scanner/Core/Inc/main.h                  	Header for main.c module
  - BLE/BLE_Scanner/STM32_WPAN/App/app_ble.h          Header for app_ble.c module
  - BLE/BLE_Scanner/Core/Inc/app_common.h            	Header for all modules with common definition
  - BLE/BLE_Scanner/Core/Inc/app_conf.h              	Parameters configuration file of the application
  - BLE/BLE_Scanner/Core/Inc/app_entry.h            	Parameters configuration file of the application
  - BLE/BLE_Scanner/STM32_WPAN/App/ble_conf.h         BLE Services configuration
  - BLE/BLE_Scanner/STM32_WPAN/App/ble_dbg_conf.h     BLE Traces configuration of the BLE services
  - BLE/BLE_Scanner/STM32_WPAN/App/p2p_client_app.h   Header for p2p_lcient_app.c module
  - BLE/BLE_Scanner/Core/Inc/hw_conf.h           		Configuration file of the HW
  - BLE/BLE_Scanner/Core/Inc/utilities_conf.h    		Configuration file of the utilities
  - BLE/BLE_Scanner/Core/Src/stm32wbxx_it.c          	Interrupt handlers
  - BLE/BLE_Scanner/Core/Src/main.c                  	Main program
  - BLE/BLE_Scanner/Core/Src/system_stm32wbxx.c      	stm32wbxx system source file
  - BLE/BLE_Scanner/STM32_WPAN/App/app_ble.c      	BLE Profile implementation -> Modify for Scanner application
  - BLE/BLE_Scanner/Core/Src/app_entry.c      		Initialization of the application
  - BLE/BLE_Scanner/STM32_WPAN/App/p2p_client_app.c   P2P Client Application Implementation -> Modify for Scanner application
  - BLE/BLE_Scanner/STM32_WPAN/Target/hw_ipcc.c      	IPCC Driver
  - BLE/BLE_Scanner/Core/Src/stm32_lpm_if.c			Low Power Manager Interface
  - BLE/BLE_Scanner/Core/Src/hw_timerserver.c 		Timer Server based on RTC
  - BLE/BLE_Scanner/Core/Src/hw_uart.c 				UART Driver
  

@par Hardware and Software environment

    - This application runs on STM32WB55xx Nucleo board
    
    - Nucleo board Set-up    
       - Connect that Board to your PC with a USB cable type A to mini-B to ST-LINK connector (USB_STLINK).
       - Please ensure that the ST-LINK connectors and jumpers are fitted.

@par How to use it ? 

This application requests having the stm32wb5x_BLE_Stack_full_fw.bin binary flashed on the Wireless Coprocessor.
If it is not the case, you need to use STM32CubeProgrammer to load the appropriate binary.
All available binaries are located under /Projects/STM32_Copro_Wireless_Binaries directory.
Refer to UM2237 to learn how to use/install STM32CubeProgrammer.
Refer to /Projects/STM32_Copro_Wireless_Binaries/ReleaseNote.html for the detailed procedure to change the
Wireless Coprocessor binary.  
   
In order to make the program work, you must do the following :
 - Open your preferred toolchain 
 - Rebuild all files and load the image into Target memory
 - OR use the BLE_p2pClient_reference.hex from Binary directory
 - This must be done for BLE_Scanner.

 - a GATT Server may be connected by a GATT Client.
 - Once the code is downloaded into the STM32WB55xx board and executed, the modules are initialized. 

 - The Central device (BLE_Scanner) starts scanning when pressing the User button (SW1). 
   - BLE_Scanner blue led becomes on. 
   - Scan req takes about 10 seconds.
 - Then, the report of all the surrounding devices is sent to the COM STLink port, it can be visualized in the terminal at a speed of 115200 Bauds. 
   - Blue led turns off.
   - The report is decomposed by the name, address and RSSI of the device.
   - You can select a device with the terminal, the number of the device.
 - A GAP connection is launched to the selected device.
   - If the connection is allowed, the green led of the scanner start blinking.
   - A list of GATT server Services appaear, with the UUID and the descriptors.
 - The connection part of the scanner is not finish, you can't use a GATT service for now.
  
For more details refer to the Application Note: 
  AN5289 - Building a Wireless application 
 
 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
