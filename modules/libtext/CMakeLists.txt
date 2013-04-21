include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libfont
  ../librender
  ../libblit
  ../libgrbase
)

add_library (
  text
  ${MODULES}
  libtext.c
) 

target_link_libraries (
  text
  bgdrtm
  font
  render
  blit
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    text
    DESTINATION
    /usr/lib
  )
endif ()
