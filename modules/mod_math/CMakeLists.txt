include_directories (
  ../../core/include
)

add_library (
  mod_math
  ${MODULES}
  mod_math.c
) 

target_link_libraries (
  mod_math
  m
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_math
    DESTINATION
    /usr/lib
  )
endif ()
