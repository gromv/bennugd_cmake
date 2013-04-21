include_directories (
  ../../core/include
)

add_library (
  mod_string
  ${MODULES}
  mod_string.c
) 

target_link_libraries (
  mod_string
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_string
    DESTINATION
    /usr/lib
  )
endif ()
