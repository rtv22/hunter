# Copyright (c) 2013-2017, Ruslan Baratov
# All rights reserved.

cmake_minimum_required(VERSION 3.0)

# Emulate HunterGate:
# * https://github.com/hunter-packages/gate
include("../common.cmake")

project(download-boost)

# download boost
hunter_add_package(Boost COMPONENTS log)

# now boost can be used
find_package(Boost CONFIG REQUIRED log)
add_executable(foo foo.cpp)
target_link_libraries(foo Boost::log)
