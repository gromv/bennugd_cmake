include_directories (
  ../../core/include
  ../libkey
)

add_library (
  mod_key
  ${MODULES}
  mod_key.c
) 

target_link_libraries (
  mod_key
  key
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_key
    DESTINATION
    /usr/lib
  )
endif ()
