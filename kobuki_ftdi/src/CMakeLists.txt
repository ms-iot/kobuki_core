##############################################################################
# Binaries
##############################################################################

add_executable(ftdi_scan ftdi_scan.cpp)
target_link_libraries(ftdi_scan ${libftdi_LIBRARIES})

add_executable(ftdi_kobuki ftdi_kobuki.cpp)
target_link_libraries(ftdi_kobuki ${libftdi_LIBRARIES})

add_executable(ftdi_read_eeprom ftdi_read_eeprom.cpp)
target_link_libraries(ftdi_read_eeprom ${libftdi_LIBRARIES})

add_executable(ftdi_write_eeprom ftdi_write_eeprom.cpp)
target_link_libraries(ftdi_write_eeprom ${libftdi_LIBRARIES})

add_executable(find_devices find_devices.cpp)
target_link_libraries(find_devices ${libusb_LIBRARIES})

add_executable(get_serial_number get_serial_number.cpp)
target_link_libraries(get_serial_number ${libusb_LIBRARIES})

add_executable(flasher flasher.cpp)
target_link_libraries(flasher ${libusb_LIBRARIES} ${libftdi_LIBRARIES})

add_executable(reset_device reset_device.cpp)
target_link_libraries(reset_device ${libusb_LIBRARIES})

add_executable(overwrite_serial_number overwrite_serial_number.cpp)
target_link_libraries(overwrite_serial_number ${libusb_LIBRARIES} ${libftdi_LIBRARIES})

add_executable(unflasher unflasher.cpp)
target_link_libraries(unflasher ${libusb_LIBRARIES} ${libftdi_LIBRARIES})

install(TARGETS ftdi_scan ftdi_kobuki ftdi_read_eeprom ftdi_write_eeprom find_devices
                get_serial_number flasher reset_device overwrite_serial_number unflasher
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
