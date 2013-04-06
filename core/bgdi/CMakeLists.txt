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
  bgdrtm
  dl
  z
  m
)

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    bgdi
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

install (
  TARGETS
  bgdi
  DESTINATION
  /usr/bin
)