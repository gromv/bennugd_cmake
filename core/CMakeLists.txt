add_subdirectory (bgdrtm)
add_subdirectory (bgdi)

if(NOT ${FILES} MATCHES "INTERPRETER_ONLY")
  add_subdirectory (bgdc)
endif ()