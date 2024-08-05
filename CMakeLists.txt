cmake_minimum_required(VERSION 3.28)
project(Pacman)

# Set C++ standard to C++17
set(CMAKE_CXX_STANDARD 17)

# Find SFML
find_package(SFML 2.5.1 COMPONENTS system window graphics REQUIRED)

# Find Boost
#find_package(Boost COMPONENTS REQUIRED)

# Add all source files in the src directory
file(GLOB_RECURSE SOURCE_FILES "src/*.cpp" "src/*.h" "src/*.hpp")
# Add the executable
add_executable(Pacman ${SOURCE_FILES})

target_include_directories(Pacman PRIVATE 
    include
)
# Link SFML libraries to the project
target_link_libraries(Pacman 
    sfml-system sfml-window sfml-graphics
)