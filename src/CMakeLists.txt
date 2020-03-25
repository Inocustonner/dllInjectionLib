cmake_minimum_required(VERSION 3.9)
include_directories("${CMAKE_SOURCE_DIR}/include")
#link_directories("${CMAKE_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE}")


add_definitions(/D_CRT_SECURE_NO_WARNINGS)
add_library(table_gui STATIC dllInj.cpp)
#force MT flags
set_property(TARGET table_gui PROPERTY
  MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>DLL")
  
#force c++latest on msvc  
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++latest")