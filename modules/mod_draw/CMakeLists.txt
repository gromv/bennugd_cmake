include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libdraw
  ../librender
  ../libblit
  ../libgrbase
)

add_library (
  mod_draw
  ${MODULES}
  mod_draw.c
) 

target_link_libraries (
  mod_draw
  bgdrtm
  draw
  render
  blit
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_draw
    DESTINATION
    /usr/lib
  )
endif ()
