cmake_minimum_required(VERSION 3.10)
project(kenslab VERSION 1.0)

find_package(SDL2 REQUIRED)

set (PSP_LIBS -lpspgu -ljpeg -lpng -lpspvfpu -lpspaudio -lpspfpu pspge pspdisplay pspvram -lGLU -lGL)

add_executable(kenslab adlibemu.c demo.c graphx.c init.c lab3d.c oldlab3d.c setup.c subs.c)
target_include_directories(kenslab PUBLIC ${SDL2_INCLUDE_DIRS})
target_link_libraries(kenslab ${SDL2_LIBRARIES} -lm -lGL -lz -lpng -lGLU -lSDL2_image ${PSP_LIBS})

