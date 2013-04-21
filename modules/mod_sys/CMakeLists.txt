include_directories (
  ../../core/include
)

add_library (
  mod_sys
  ${MODULES}
  mod_sys.c
) 

target_link_libraries (
  mod_sys
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_sys
    DESTINATION
    /usr/lib
  )
endif ()
