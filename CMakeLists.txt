cmake_minimum_required(VERSION 3.13...3.27)

set(PROJECT_NAME hello_usb)

# initialize pico-sdk from submodule
# note: this must happen before project()
include(pico-sdk/pico_sdk_init.cmake)

# initialize the Raspberry Pi Pico SDK
project(${PROJECT_NAME} C CXX ASM)
pico_sdk_init()

# rest of your project
add_subdirectory(src)

