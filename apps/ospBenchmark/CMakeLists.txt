## Copyright 2018-2020 Intel Corporation
## SPDX-License-Identifier: Apache-2.0

if (NOT OSPRAY_APPS_TESTING)
  return()
endif()

add_executable(ospBenchmark
  ${OSPRAY_RESOURCE}

  ospBenchmark.cpp
  BaseFixture.cpp

  benchmarks/BoxesAo.cpp
  benchmarks/CornellBoxSpp.cpp
  benchmarks/GravitySpheresVolume.cpp
  benchmarks/PerlinNoiseVolumes.cpp
  benchmarks/ClippingGeometries.cpp
)

target_link_libraries(ospBenchmark
PRIVATE
  arcball_camera
  benchmark
  ospray_testing
)

install(TARGETS ospBenchmark
  DESTINATION ${CMAKE_INSTALL_BINDIR}
  COMPONENT apps
)
