CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT (BennuGD)
SET (BENNUGD_VERSION 1.0.0)

set (CMAKE_C_FLAGS "-Wall ${CMAKE_C_FLAGS}")
#set (CMAKE_C_FLAGS_DEBUG "-Werror ${CMAKE_C_FLAGS_DEBUG}")

add_definitions (
  -DTARGET_LINUX
  -DVERSION="1.0.0"
)

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

INSTALL_TARGETS (/usr/bin core/bgdc/bgdc)
INSTALL_TARGETS (/usr/bin core/bgdi/bgdi)
INSTALL_TARGETS (/usr/lib core/bgdrtm/libbgdrtm.so)
INSTALL_TARGETS (/usr/lib modules/*.so)