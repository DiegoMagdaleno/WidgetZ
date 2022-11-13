add_executable(widgetz_example example.c)

target_link_libraries(widgetz_example PRIVATE widgetzStatic)
target_include_directories(widgetz_example PRIVATE ${ALLEGRO_INCLUDE_DIR})
target_link_libraries(widgetz_example PRIVATE ${ALLEGRO_LIBRARIES})

INSTALL(TARGETS widgetz_example DESTINATION bin)

