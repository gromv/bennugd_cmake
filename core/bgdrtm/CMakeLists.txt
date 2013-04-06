include_directories (
  include
  ../bgdc/include
)

add_definitions (-D__BGDRTM__)

add_library (
  bgdrtm
  ${MODULES}
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
  ../common/b_crypt.c
) 

target_link_libraries (
  bgdrtm
  crypto  
)

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    bgdrtm
    grbase
    bgload
    blit
    draw
    video
    render
    font
    text
    sdlhandler
    wm
    key
    mouse
    joy
    scroll
    mod_scroll
    mod_mouse
    mod_map
    mod_video
    mod_screen
    mod_blendop
    mod_text
    mod_draw
    mod_grproc
    mod_effects
    mod_key
    mod_cd
    mod_dir
    mod_file
    mod_crypt
    mod_joy
    mod_math
    mod_mem
    mod_proc
    mod_rand
    mod_regex
    mod_say
    mod_sort
    mod_sound
    mod_string
    mod_sys
    mod_time
    mod_timers
    mod_path
    mod_wm
    mod_debug
    mod_flic
    mod_m7    
  )
endif ()

if (${MODULES} MATCHES "SHARED")
  install (
    TARGETS
    bgdrtm
    DESTINATION
    /usr/lib
  )
endif ()