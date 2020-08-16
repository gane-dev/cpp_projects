cmake_minimum_required(VERSION 3.10)

# set the project name
project(httpclient_async)

# add the executable
find_package(Boost COMPONENTS system)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
add_executable(httpclient_async async_httpclient.cpp)
# target_link_libraries(io_context Boost::async_wait)
target_compile_features(httpclient_async PRIVATE cxx_std_17)
endif()
