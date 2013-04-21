include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libjoy
)

add_library (
  mod_joy
  ${MODULES}
  mod_joy.c
) 

target_link_libraries (
  mod_joy
  joy
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_joy
    DESTINATION
    /usr/lib
  )
endif ()
