#
# Copyright 2010-2015 Ettus Research LLC
# Copyright 2018 Ettus Research, a National Instruments Company
#
# SPDX-License-Identifier: GPL-3.0-or-later
cmake_minimum_required(VERSION 3.16)

list(INSERT CMAKE_MODULE_PATH 0 ${CMAKE_SOURCE_DIR}/cmake/Modules)

project(bladerfrec)
set(CMAKE_BUILD_TYPE Release)
add_executable(bladerfrec bladerfrec.cc)

find_package(PkgConfig REQUIRED)
find_package(LibbladeRF)
find_package(Boost ${Boost_Version} COMPONENTS iostreams thread program_options filesystem REQUIRED)
target_link_libraries(bladerfrec LINK_PUBLIC ${LIBBLADERF_LIBRARIES} ${Boost_LIBRARIES})
