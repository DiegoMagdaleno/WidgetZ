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

target_include_directories(widgetz PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/../include")
target_link_libraries(widgetz PRIVATE unofficial-allegro5 freetype)

install(TARGETS widgetz DESTINATION lib)
install(DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../include" DESTINATION include)