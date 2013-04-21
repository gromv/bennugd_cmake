include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libbgload
)

add_library (
  mod_sound
  ${MODULES}
  mod_sound.c
) 

target_link_libraries (
  mod_sound
  SDL
  bgload
  bgdrtm
  SDL_mixer
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_sound
    DESTINATION
    /usr/lib
  )
endif ()
