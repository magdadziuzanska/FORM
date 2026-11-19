cmake_minimum_required(VERSION 3.20)
project(FORM VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(form src/main.cpp)

# --- Testy ---
include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/refs/tags/v1.17.0.zip
  DOWNLOAD_EXTRACT_TIMESTAMP TRUE
)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()
add_executable(form_tests tests/test_przyklad.cpp)
target_link_libraries(form_tests GTest::gtest_main)
include(GoogleTest)
gtest_discover_tests(form_tests)