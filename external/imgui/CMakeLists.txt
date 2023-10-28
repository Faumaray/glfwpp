add_library (Imgui
        imgui/imgui.h
        imgui/imgui.cpp
        imgui/imconfig.h
        imgui/imgui_demo.cpp
        imgui/imgui_draw.cpp
        imgui/imgui_internal.h
        imgui/imgui_tables.cpp
        imgui/imgui_widgets.cpp
        imgui/imstb_rectpack.h
        imgui/imstb_textedit.h
        imgui/imstb_truetype.h
        imgui/backends/imgui_impl_glfw.cpp
        imgui/backends/imgui_impl_glfw.h
        imgui/backends/imgui_impl_opengl3.cpp
        imgui/backends/imgui_impl_opengl3_loader.h
        imgui/backends/imgui_impl_opengl3.h
        )
target_include_directories(Imgui PUBLIC
        imgui
        imgui/backends
        )
target_link_libraries(Imgui PUBLIC glfw libglew_static)

if (WIN32 AND NOT (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC"))
        target_link_libraries(Imgui PUBLIC "Imm32.lib")
endif()
