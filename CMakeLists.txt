project(webview_cmake VERSION 0.0.1)

add_library(webview INTERFACE)
target_include_directories(webview INTERFACE include)

if (AMD64 STREQUAL ${CMAKE_SYSTEM_PROCESSOR})
    set(ARCH x64)
else()
    set(ARCH x86)
    #[[TODO: handle arm64 ...]]
endif()
message(STATUS webview-architecture=${ARCH})

add_library(webview_static INTERFACE)
target_include_directories(webview_static INTERFACE include)
target_link_directories(webview_static INTERFACE ${ARCH})
target_link_libraries(webview_static INTERFACE WebView2LoaderStatic)