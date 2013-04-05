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

INSTALL(
  TARGETS
    core/bgdc/bgdc
    core/bgdi/bgdi
    core/bgdrtm/libbgdrtm.so
    modules/*.so
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
)