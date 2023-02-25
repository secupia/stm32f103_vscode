# STM32F103 using VSCode & CMake

Setup STM32F103 Development Environment

1. Setup tools

 1.1 Visual Studio Code
   - add extension : C/C++, CMake & CMake Tools, Cortex-Debug
   
 1.2 Compilier  : gcc-arm-none-eabi-9-2020-q2-update-win32
 
 1.3 Build tool : 
   - ninja-win-v1.11.1 : Result OK
   - xpack-windows-build-tools-4.2.1-2 : Result Fail
   
 1.4 GDB Server : xpack-openocd-0.10.0-15

2. Configure tools

 2.1 CMake Tools
   -Cmake:Configure Args
    [-DARM_TOOLCHAIN_DIR=D:/tools/gcc-arm-none-eabi-9-2020-q2-update-win32/bin]
    [-DCMAKE_MAKE_PROGRAM=D:/tools/ninja-win-v1.11.1/ninja.exe]
   
   -CMake: Generator
    [Ninja]
    
 2.2 Cortex-Debug
   - Cortex-debug:Arm Toolchain Path
{
	"folders": [
		{
			"path": "stm32f103_fw"
		}
	],
	"settings": {
		"cmake.configureArgs": [
			"-DARM_TOOLCHAIN_DIR=D:/tools/gcc-arm-none-eabi-9-2020-q2-update-win32/bin",
			"-DCMAKE_MAKE_PROGRAM=D:/tools/ninja-win-v1.11.1/ninja.exe"
		],
		"cmake.generator": "Ninja",
		"cortex-debug.armToolchainPath": "D:/tools/gcc-arm-none-eabi-9-2020-q2-update-win32/bin",
		"cortex-debug.openocdPath": "D:/tools/xpack-openocd-0.10.0-15/bin/openocd",
	}
}

   - Cortex-debug:Openocd Path
{
	"folders": [
		{
			"path": "stm32f103_fw"
		}
	],
	"settings": {
		"cmake.configureArgs": [
			"-DARM_TOOLCHAIN_DIR=D:/tools/gcc-arm-none-eabi-9-2020-q2-update-win32/bin",
			"-DCMAKE_MAKE_PROGRAM=D:/tools/ninja-win-v1.11.1/ninja.exe"
		],
		"cmake.generator": "Ninja",
		"cortex-debug.armToolchainPath": "D:/tools/gcc-arm-none-eabi-9-2020-q2-update-win32/bin",
		"cortex-debug.openocdPath": "D:/tools/xpack-openocd-0.10.0-15/bin/openocd",
	}
}

3. Setup project

 3.1 vscode folder
 
   - cmake-kits.json
   - launch.json
   
 3.2 tools folder
 
    arm-none-eabi-gcc.cmake
    
 3.3 clangd
   - inlay hints : off

4. Reference

  - https://code.visualstudio.com/docs 
  - https://cmake.org/cmake/help/latest
  - https://ninja-build.org/
