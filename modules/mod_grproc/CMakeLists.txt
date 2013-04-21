include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../librender
  ../libblit
  ../libvideo
  ../libgrbase
  ../libscroll
)

add_library (
  mod_grproc
  ${MODULES}
  mod_grproc.c
) 

target_link_libraries (
  mod_grproc
  bgdrtm
  render
  blit
  video
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_grproc
    DESTINATION
    /usr/lib
  )
endif ()
