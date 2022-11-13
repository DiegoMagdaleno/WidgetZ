add_executable(widgetz_example example.c)

target_link_libraries(widgetz_example PRIVATE widgetz)

INSTALL(TARGETS widgetz_example DESTINATION bin)
