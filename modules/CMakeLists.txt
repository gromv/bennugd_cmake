include_directories (
  libgrbase
  libblit
  librender
  libvideo
  libbgload
  libfont
  libscroll
  libkey
  libjoy
  libdraw
  libtext
)

add_library (
  bgload
  ${MODULES}
  libbgload/bgload.c
) 

add_library (
  blit
  ${MODULES}
  libblit/libblit.c
  libblit/g_blit.c
  libblit/g_pixel.c
) 

add_library (
  draw
  ${MODULES}
  libdraw/libdraw.c
) 

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    draw
    blit
  )
endif ()

add_library (
  font
  ${MODULES}
  libfont/libfont.c
) 

add_library (
  grbase
  ${MODULES}
  libgrbase/g_bitmap.c
  libgrbase/g_blendop.c
  libgrbase/g_clear.c
  libgrbase/g_conversion.c
  libgrbase/g_grlib.c
  libgrbase/g_pal.c
  libgrbase/libgrbase.c
) 

add_library (
  joy
  ${MODULES}
  libjoy/libjoy.c
) 

add_library (
  key
  ${MODULES}
  libkey/libkey.c
) 

add_library (
  mouse
  ${MODULES}
  libmouse/libmouse.c
) 

add_definitions(-D__LIBRENDER)

add_library (
  render
  ${MODULES}
  librender/g_fade.c
  librender/g_frame.c
  librender/g_instance.c
  librender/g_object.c
  librender/g_rects.c
  librender/g_screen.c
  librender/librender.c
  librender/scaler_hq2x.c
  librender/scaler_normal.c
  librender/scaler_scale2x.c
  librender/scaler_scanline.c
) 

add_library (
  scroll
  ${MODULES}
  libscroll/libscroll.c
) 

add_library (
  sdlhandler
  ${MODULES}
  libsdlhandler/libsdlhandler.c
) 

add_library (
  text
  ${MODULES}
  libtext/libtext.c
) 

add_library (
  video
  ${MODULES}
  libvideo/g_regions.c
  libvideo/g_video.c
) 

target_link_libraries (
  video
  SDL
)

add_library (
  wm
  ${MODULES}
  libwm/libwm.c
) 

add_library (
  mod_blendop
  ${MODULES}
  mod_blendop/mod_blendop.c
) 

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    mod_blendop
    grbase
  )
endif ()

add_library (
  mod_cd
  ${MODULES}
  mod_cd/mod_cd.c
) 

add_library (
  mod_crypt
  ${MODULES}
  mod_crypt/mod_crypt.c
) 

add_library (
  mod_debug
  ${MODULES}
  mod_debug/mod_debug.c
  mod_debug/systexts.c
)

add_library (
  mod_dir
  ${MODULES}
  mod_dir/mod_dir.c
) 

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    mod_dir
    bgdrtm
  )
endif ()

add_library (
  mod_draw
  ${MODULES}
  mod_draw/mod_draw.c
) 

if (${MODULES} MATCHES "STATIC")
  target_link_libraries (
    mod_draw
    draw
  )
endif ()

add_library (
  mod_effects
  ${MODULES}
  mod_effects/mod_effects.c
) 

add_library (
  mod_file
  ${MODULES}
  mod_file/mod_file.c
) 

add_library (
  mod_flic
  ${MODULES}
  mod_flic/mod_flic.c
) 

add_library (
  mod_grproc
  ${MODULES}
  mod_grproc/mod_grproc.c
) 

add_library (
  mod_joy
  ${MODULES}
  mod_joy/mod_joy.c
) 

add_library (
  mod_key
  ${MODULES}
  mod_key/mod_key.c
) 

add_library (
  mod_m7
  ${MODULES}
  mod_m7/mod_m7.c
) 

add_library (
  mod_map
  ${MODULES}
  mod_map/mod_map.c
  mod_map/file_fnt.c
  mod_map/file_fpg.c
  mod_map/file_map.c
  mod_map/file_pal.c
  mod_map/file_pcx.c
  mod_map/file_png.c
) 

target_link_libraries (
  mod_map
  png
)

add_library (
  mod_math
  ${MODULES}
  mod_math/mod_math.c
) 

add_library (
  mod_mathi
  ${MODULES}
  mod_mathi/mod_mathi.c
) 

add_library (
  mod_mem
  ${MODULES}
  mod_mem/mod_mem.c
) 

add_library (
  mod_mouse
  ${MODULES}
  mod_mouse/mod_mouse.c
) 

add_library (
  mod_path
  ${MODULES}
  mod_path/mod_path.c
) 

add_library (
  mod_proc
  ${MODULES}
  mod_proc/mod_proc.c
) 

add_library (
  mod_rand
  ${MODULES}
  mod_rand/mod_rand.c
) 

add_library (
  mod_regex
  ${MODULES}
  mod_regex/mod_regex.c
  mod_regex/regex.c
) 

add_library (
  mod_say
  ${MODULES}
  mod_say/mod_say.c
) 

add_library (
  mod_screen
  ${MODULES}
  mod_screen/mod_screen.c
) 

add_library (
  mod_scroll
  ${MODULES}
  mod_scroll/mod_scroll.c
) 

add_library (
  mod_sort
  ${MODULES}
  mod_sort/mod_sort.c
) 

add_library (
  mod_sound
  ${MODULES}
  mod_sound/mod_sound.c
) 

target_link_libraries (
  mod_sound
  SDL_mixer
  bgload
)

add_library (
  mod_string
  ${MODULES}
  mod_string/mod_string.c
) 

add_library (
  mod_sys
  ${MODULES}
  mod_sys/mod_sys.c
) 

add_library (
  mod_text
  ${MODULES}
  mod_text/mod_text.c
) 

add_library (
  mod_time
  ${MODULES}
  mod_time/mod_time.c
) 

add_library (
  mod_timers
  ${MODULES}
  mod_timers/mod_timers.c
) 

add_library (
  mod_video
  ${MODULES}
  mod_video/mod_video.c
) 

add_library (
  mod_wm
  ${MODULES}
  mod_wm/mod_wm.c
)

if (${MODULES} MATCHES "SHARED")
  install (
    TARGETS
    bgload
    blit
    draw
    font
    grbase
    joy
    key
    mouse
    render
    scroll
    sdlhandler
    text
    video
    wm
    mod_blendop
    mod_cd
    mod_crypt
    mod_debug
    mod_dir
    mod_draw
    mod_effects
    mod_file
    mod_flic
    mod_grproc
    mod_joy
    mod_key
    mod_m7
    mod_map
    mod_math
    mod_mathi
    mod_mem
    mod_mouse
    mod_path
    mod_proc
    mod_rand
    mod_regex
    mod_say
    mod_screen
    mod_scroll
    mod_sort
    mod_sound
    mod_string
    mod_sys
    mod_text
    mod_time
    mod_timers
    mod_video
    mod_wm
    DESTINATION
    /usr/lib
  )
endif ()