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
  SHARED
  libbgload/bgload.c
) 

add_library (
  blit
  SHARED
  libblit/libblit.c
  libblit/g_blit.c
  libblit/g_pixel.c
) 

add_library (
  draw
  SHARED
  libdraw/libdraw.c
) 

add_library (
  font
  SHARED
  libfont/libfont.c
) 

add_library (
  grbase
  SHARED
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
  SHARED
  libjoy/libjoy.c
) 

add_library (
  key
  SHARED
  libkey/libkey.c
) 

add_library (
  mouse
  SHARED
  libmouse/libmouse.c
) 

add_definitions(-D__LIBRENDER)

add_library (
  render
  SHARED
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
  SHARED
  libscroll/libscroll.c
) 

add_library (
  sdlhandler
  SHARED
  libsdlhandler/libsdlhandler.c
) 

add_library (
  text
  SHARED
  libtext/libtext.c
) 

add_library (
  video
  SHARED
  libvideo/g_regions.c
  libvideo/g_video.c
) 

target_link_libraries (
  video
  SDL
)

add_library (
  wm
  SHARED
  libwm/libwm.c
) 

add_library (
  mod_blendop
  SHARED
  mod_blendop/mod_blendop.c
) 

add_library (
  mod_cd
  SHARED
  mod_cd/mod_cd.c
) 

add_library (
  mod_crypt
  SHARED
  mod_crypt/mod_crypt.c
) 

add_library (
  mod_debug
  SHARED
  mod_debug/mod_debug.c
  mod_debug/systexts.c
)

add_library (
  mod_dir
  SHARED
  mod_dir/mod_dir.c
) 

add_library (
  mod_draw
  SHARED
  mod_draw/mod_draw.c
) 

add_library (
  mod_effects
  SHARED
  mod_effects/mod_effects.c
) 

add_library (
  mod_file
  SHARED
  mod_file/mod_file.c
) 

add_library (
  mod_flic
  SHARED
  mod_flic/mod_flic.c
) 

add_library (
  mod_grproc
  SHARED
  mod_grproc/mod_grproc.c
) 

add_library (
  mod_joy
  SHARED
  mod_joy/mod_joy.c
) 

add_library (
  mod_key
  SHARED
  mod_key/mod_key.c
) 

add_library (
  mod_m7
  SHARED
  mod_m7/mod_m7.c
) 

add_library (
  mod_map
  SHARED
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
  SHARED
  mod_math/mod_math.c
) 

add_library (
  mod_mathi
  SHARED
  mod_mathi/mod_mathi.c
) 

add_library (
  mod_mem
  SHARED
  mod_mem/mod_mem.c
) 

add_library (
  mod_mouse
  SHARED
  mod_mouse/mod_mouse.c
) 

add_library (
  mod_path
  SHARED
  mod_path/mod_path.c
) 

add_library (
  mod_proc
  SHARED
  mod_proc/mod_proc.c
) 

add_library (
  mod_rand
  SHARED
  mod_rand/mod_rand.c
) 

add_library (
  mod_regex
  SHARED
  mod_regex/mod_regex.c
  mod_regex/regex.c
) 

add_library (
  mod_say
  SHARED
  mod_say/mod_say.c
) 

add_library (
  mod_screen
  SHARED
  mod_screen/mod_screen.c
) 

add_library (
  mod_scroll
  SHARED
  mod_scroll/mod_scroll.c
) 

add_library (
  mod_sort
  SHARED
  mod_sort/mod_sort.c
) 

add_library (
  mod_sound
  SHARED
  mod_sound/mod_sound.c
) 

target_link_libraries (
  mod_sound
  SDL_mixer
  bgload
)

add_library (
  mod_string
  SHARED
  mod_string/mod_string.c
) 

add_library (
  mod_sys
  SHARED
  mod_sys/mod_sys.c
) 

add_library (
  mod_text
  SHARED
  mod_text/mod_text.c
) 

add_library (
  mod_time
  SHARED
  mod_time/mod_time.c
) 

add_library (
  mod_timers
  SHARED
  mod_timers/mod_timers.c
) 

add_library (
  mod_video
  SHARED
  mod_video/mod_video.c
) 

add_library (
  mod_wm
  SHARED
  mod_wm/mod_wm.c
)