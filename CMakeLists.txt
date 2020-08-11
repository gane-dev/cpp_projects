cmake_minimum_required(VERSION 3.10)

# set the project name
project(programoptions)

# add the executable
find_package(Boost COMPONENTS program_options)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
add_executable(programoptions programoptions.cpp)
target_link_libraries(programoptions Boost::program_options)
target_compile_features(programoptions PRIVATE cxx_std_17)
endif()
