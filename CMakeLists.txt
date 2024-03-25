# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.
cmake_minimum_required(VERSION 3.14)
project(d3d12translationlayer)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(DirectX-Headers)
option(USE_PIX "Enable the use of PIX markers" ON)

add_subdirectory(src)

if (HAS_WDK)
    add_subdirectory(DxbcParser)
    target_link_libraries(d3d12translationlayer dxbcparser)
endif()
