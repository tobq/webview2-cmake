project(webview_cmake VERSION 0.0.1)

add_library(webview INTERFACE)
target_include_directories(webview INTERFACE include)

add_library(webview_static INTERFACE)
target_include_directories(webview_static INTERFACE include)
target_link_directories(webview_static INTERFACE x64)
target_link_libraries(webview_static INTERFACE WebView2LoaderStatic)