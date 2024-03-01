# Copyright (c) 2018-2022 Margarita Colberg
# SPDX-License-Identifier: BSD-3-Clause

#-----------------------------------------------------------------------------------------------------

# create common library with all dependant source files for main
add_library(hybridmc_common OBJECT molecule.cc hardspheres.cc crankshaft.cc entropy.cc config.cc snapshot.cc main_helpers.cc)

target_include_directories(hybridmc_common SYSTEM PUBLIC ${Boost_INCLUDE_DIRS} ${HDF5_INCLUDE_DIRS})

# Assign common libraries to hybridmc_common
target_link_libraries(hybridmc_common PUBLIC ${Boost_LIBRARIES} ${HDF5_LIBRARIES})

#--------------------------------------------------------------
#pybind11 method for making wang landau port:
pybind11_add_module(wang_landau wang_landau.cc)
target_link_libraries(wang_landau PRIVATE hybridmc_common)
target_compile_definitions(wang_landau
        PRIVATE VERSION_INFO=${EXAMPLE_VERSION_INFO})
#------------------------------------------------------------
