include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libgrbase
)

add_library (
  font
  ${MODULES}
  libfont.c
) 

target_link_libraries (
  font
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    font
    DESTINATION
    /usr/lib
  )
endif ()