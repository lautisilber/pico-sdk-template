add_executable(${PROJECT_NAME}
            hello_usb.c
            )

if (NOT TARGET tinyusb_device)
    message(FATAL_ERROR "Won't be able to output serial through USB because TinyUSB submodule is not initialized in the SDK")
endif()

# pull in common dependencies
target_link_libraries(${PROJECT_NAME} pico_stdlib)

# enable usb output, disable uart output
pico_enable_stdio_usb(${PROJECT_NAME} 1)
pico_enable_stdio_uart(${PROJECT_NAME} 0)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(${PROJECT_NAME})