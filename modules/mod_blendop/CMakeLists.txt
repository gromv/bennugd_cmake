include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libgrbase
)

add_library (
  mod_blendop
  ${MODULES}
  mod_blendop.c
) 

target_link_libraries (
  mod_blendop
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_blendop
    DESTINATION
    /usr/lib
  )
endif ()
