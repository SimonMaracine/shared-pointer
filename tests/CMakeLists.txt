cmake_minimum_required(VERSION 3.20)

set(INSTALL_GTEST OFF)
set(BUILD_GMOCK OFF)

add_subdirectory(extern/googletest)

add_executable(main "main.cpp")

target_link_libraries(main PRIVATE shared_pointer GTest::gtest_main)

target_compile_options(main PRIVATE "-Wall" "-Wextra" "-Wpedantic" "-fno-elide-constructors")

target_compile_features(main PRIVATE cxx_std_17)
set_target_properties(main PROPERTIES CXX_EXTENSIONS OFF)
