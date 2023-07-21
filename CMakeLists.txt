# CMakeList.txt : CMakeApplicationSample の CMake プロジェクト。ソースを含めて、次を定義します:
# プロジェクト専用ロジックはこちらです。
#
cmake_minimum_required (VERSION 3.8)

project ("CMakeApplicationSample")

find_package(CMakeLibraryProject 0.1.0 REQUIRED)

# ソースをこのプロジェクトの実行可能ファイルに追加します。
add_executable (CMakeApplicationSample "CMakeApplicationSample.cpp" "CMakeApplicationSample.h")

target_link_libraries(${PROJECT_NAME} PRIVATE CMakeLibraryProject::CMakeLibraryProject)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET CMakeApplicationSample PROPERTY CXX_STANDARD 20)
endif()

