CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

project (BennuGD)
add_definitions (-DVERSION="1.0.0")

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
  add_definitions (-DTARGET_LINUX)
endif()

if (${MODULES} MATCHES "STATIC")
  add_definitions (-D__STATIC__)
else ()
  set (MODULES "SHARED")
endif()

set (CMAKE_C_FLAGS "-Wall ${CMAKE_C_FLAGS}")
#set (CMAKE_C_FLAGS_DEBUG "-Werror ${CMAKE_C_FLAGS_DEBUG}")

find_package(SDL REQUIRED)
find_package(ZLIB REQUIRED)

include_directories (
  ${SDL_INCLUDE_DIR}
  ${ZLIB_INCLUDE_DIR}
  core/include
  core/bgdrtm/include
)

add_subdirectory (modules)
add_subdirectory (core)