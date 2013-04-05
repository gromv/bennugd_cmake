include_directories (
  include
  ../bgdc/include
)

add_definitions (-D__BGDRTM__)

add_library (
  bgrtm
  SHARED
  src/copy.c
  src/dcbr.c
  src/dirs.c
  src/fmath.c
  src/instance.c
  src/interpreter.c
  src/misc.c
  src/strings.c
  src/sysprocs.c
  src/varspace_file.c
  ../common/files.c
  ../common/xctype.c
  ../common/debug.c
) 