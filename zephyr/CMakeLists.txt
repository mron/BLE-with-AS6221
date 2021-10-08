# SPDX-License-Identifier: Apache-2.0

# set(ZEPHYR_EXTRA_MODULES "/Users/ron/Documents/PlatformIO/Projects/211002-220453-zephyr-ble-beacon/drivers/sensor/as6221" ) 
# set(ZEPHYR_EXTRA_MODULES "../drivers" ) 
message(STATUS "-------------------------   zephyr base $ENV{ZEPHYR_BASE}")

cmake_minimum_required(VERSION 3.13.1)
# cmake_minimum_required(VERSION 3.20.0)
# find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

set(DTC_OVERLAY_FILE "boards/nrf52840_i2c.overlay;boards/file2.overlay")
include($ENV{ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)
project(beacon)

# message("....... Adding sub dir")
# add_subdirectory(dts)
# add_subdirectory(drivers)

target_sources(app PRIVATE ../src/main.c)
