include_directories (
  ../../core/include
)

add_library (
  sdlhandler
  ${MODULES}
  libsdlhandler.c
) 

target_link_libraries (
  sdlhandler
  SDL
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    sdlhandler
    DESTINATION
    /usr/lib
  )
endif ()
