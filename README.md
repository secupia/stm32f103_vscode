# stm32f103_vscode

Setup STM32F103 Development Environment

1. Setup tools

 1)Visual Studio Code
   - add extension : C/C++, CMake & CMake Tools, Cortex-Debug
   
 2)Compilier  : gcc-arm-none-eabi-9-2020-q2-update-win32
 
 3)Build tool : 
   - ninja-win-v1.11.1 : Result OK
   - xpack-windows-build-tools-4.2.1-2 : Result Fail
   
 4)GDB Server : xpack-openocd-0.10.0-15

2. Configure tools

 1)CMake Tools
 
 2)Cortex-Debug
 
3. Setup project

 1).vscode folder
   - cmake-kits.json
   - launch.json
   
 2)tools folder
    arm-none-eabi-gcc.cmake
