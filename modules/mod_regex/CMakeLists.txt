include_directories (
  ../../core/include
  ../../core/bgdrtm/include
)

add_library (
  mod_regex
  ${MODULES}
  mod_regex.c
  regex.c
  #mod_regex.def
) 

target_link_libraries (
  mod_regex
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_regex
    DESTINATION
    /usr/lib
  )
endif ()
