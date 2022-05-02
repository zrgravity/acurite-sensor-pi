cmake_minimum_required(VERSION 3.0.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(acurite-sensor-pi main.cpp AdafruitIoFeed.cpp Message.cpp MessageQueue.cpp Sensor.cpp)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
target_link_libraries(acurite-sensor-pi PRIVATE Threads::Threads curlpp curl wiringPi)