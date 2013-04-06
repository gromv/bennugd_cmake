include_directories (
  include
)

add_definitions (-D__BGDC__)

add_executable (
  bgdc
  src/c_code.c
  src/c_data.c
  src/c_debug.c
  src/c_main.c
  src/codeblock.c
  src/constants.c
  src/dcbw.c
  src/error.c
  src/identifier.c
  src/main.c
  src/main_core.c
  src/procedure.c
  src/segment.c
  src/strings.c
  src/sysstub.c
  src/token.c
  src/typedef.c
  src/varspace.c
  ../common/debug.c
  ../common/b_crypt.c
  ../common/files.c
  ../common/xctype.c
)

target_link_libraries (
  bgdc
  z
  dl
  crypto
)

install (
  TARGETS
  bgdc
  DESTINATION
  /usr/bin
)