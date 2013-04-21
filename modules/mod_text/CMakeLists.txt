include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libtext
  ../libfont
  ../libgrbase
)

add_library (
  mod_text
  ${MODULES}
  mod_text.c
) 

target_link_libraries (
  mod_text
  bgdrtm
  text
  font
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_text
    DESTINATION
    /usr/lib
  )
endif ()
