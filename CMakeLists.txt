CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

project (BennuGD)
add_definitions (-DVERSION="1.0.0")

# param:
# STATIC_MODULES (instead of shared modules)
# INTERPRETER_ONLY (generate only bgdi exec)
# USE_LIBDES (instead OpenSSL, not tested)
# NO_SOUND (not tested)

# gcw0 param to add in builtroot
set (STATIC_MODULES true)
set (INTERPRETER_ONLY true)
set (USE_LIBDES false)
set (NO_SOUND false)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
  add_definitions (-DTARGET_LINUX)
endif()

if (STATIC_MODULES)
  add_definitions (-D__STATIC__)
  set (MODULES "STATIC")
else ()
  set (MODULES "SHARED")
endif ()

if (NO_SOUND)
  add_definitions (-DNO_SOUND)
endif ()

find_package (SDL REQUIRED)
find_package (ZLIB REQUIRED)
if (USE_LIBDES)
  add_definitions (-DUSE_LIBDES)
else ()
  find_package(OpenSSL REQUIRED)
  add_definitions (-DUSE_OPENSSL)
endif ()

include_directories (
  ${SDL_INCLUDE_DIR}
  ${ZLIB_INCLUDE_DIR}
)

if (USE_LIBDES)
  add_subdirectory (3rdparty)
endif ()
add_subdirectory (modules)
add_subdirectory (core)
