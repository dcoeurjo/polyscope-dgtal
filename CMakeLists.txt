project(polyscope-dgtal)
CMAKE_MINIMUM_REQUIRED(VERSION 3.11)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(deps)

##DGtal Specific settings
include("${PROJECT_BINARY_DIR}/deps/DGtal/DGtalConfig.cmake")
include_directories("${DGTAL_INCLUDE_DIRS}")

add_executable(simpleTest simpleTest.cpp)
target_link_libraries(simpleTest polyscope DGtal ${DGTAL_LIBRARIES})
