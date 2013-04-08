include_directories (
  include
)

if (${MODULES} MATCHES "STATIC")
  include_directories (
    ../../modules/libgrbase
    ../../modules/libvideo
    ../../modules/libblit
    ../../modules/librender
    ../../modules/libfont
    ../../modules/libtext
    ../../modules/libwm
    ../../modules/libkey
    ../../modules/libmouse
    ../../modules/libjoy
    ../../modules/libscroll
    ../../modules/mod_scroll
    ../../modules/mod_mouse
    ../../modules/mod_map
    ../../modules/mod_video
    ../../modules/mod_screen
    ../../modules/mod_blendop
    ../../modules/mod_text
    ../../modules/mod_draw
    ../../modules/mod_grproc
    ../../modules/mod_effects
    ../../modules/mod_key
    ../../modules/mod_cd
    ../../modules/mod_dir
    ../../modules/mod_file
    ../../modules/mod_crypt
    ../../modules/mod_joy
    ../../modules/mod_math
    ../../modules/mod_mem
    ../../modules/mod_proc
    ../../modules/mod_rand
    ../../modules/mod_regex
    ../../modules/mod_say
    ../../modules/mod_sort
    ../../modules/mod_sound
    ../../modules/mod_string
    ../../modules/mod_sys
    ../../modules/mod_time
    ../../modules/mod_timers
    ../../modules/mod_path
    ../../modules/mod_wm
    ../../modules/mod_debug
    ../../modules/mod_flic
    ../../modules/mod_m7
  )
endif ()

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