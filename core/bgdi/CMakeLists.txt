include_directories (
  include
)

add_definitions (-D__BGDI__)

add_executable (
  bgdi
  src/main.c
)

target_link_libraries (
  bgdi
  ${CMAKE_DL_LIBS}
)

target_link_libraries (
  bgdi
  bgrtm
  dl
  z
  m
)