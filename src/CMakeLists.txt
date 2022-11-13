list(APPEND source_code
    internal_utils.c
    nine_patch.c
    skin_theme.c
    theme.c
    utils.c
    widgets/widget.c
    widgets/box.c
    widgets/button.c
    widgets/editbox.c
    widgets/filllayout.c
    widgets/layoutstop.c
    widgets/scroll.c
    widgets/textbox.c
    widgets/toggle.c
)

add_library(
    widgetz
    SHARED
    ${source_code}
)

add_library(
    widgetzStatic
    STATIC
    ${source_code}
)

set_target_properties(widgetzStatic PROPERTIES OUTPUT_NAME widgetz)

target_include_directories(widgetzStatic PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/../include")
target_include_directories(widgetzStatic PRIVATE ${ALLEGRO_INCLUDE_DIR})
target_include_directories(widgetzStatic PRIVATE ${FREETYPE_INCLUDE_DIR})


target_include_directories(widgetz PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/../include")
target_link_libraries(widgetz PRIVATE ${ALLEGRO_LIBRARIES})
target_link_libraries(widgetz PRIVATE ${FREETYPE_LIBRARIES})
target_include_directories(widgetz PRIVATE ${ALLEGRO_INCLUDE_DIR})
target_include_directories(widgetz PRIVATE ${FREETYPE_INCLUDE_DIR})

if(WIN32)
install(TARGETS widgetz DESTINATION bin)
else(WIN32)
install(TARGETS widgetz DESTINATION lib)
endif(WIN32)

install(TARGETS widgetzStatic DESTINATION lib)

install(DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../include" DESTINATION include)
