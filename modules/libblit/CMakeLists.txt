include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libgrbase
)

add_library (
  blit
  ${MODULES}
  libblit.c
  g_blit.c
  g_pixel.c
) 

target_link_libraries (
  blit
  bgdrtm
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    blit
    DESTINATION
    /usr/lib
  )
endif ()