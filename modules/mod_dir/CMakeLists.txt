include_directories (
  ../../core/include
)

add_library (
  mod_dir
  ${MODULES}
  mod_dir.c
) 

target_link_libraries (
  mod_dir
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_dir
    DESTINATION
    /usr/lib
  )
endif ()
