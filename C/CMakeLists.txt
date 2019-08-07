cmake_minimum_required(VERSION 2.6)

project (ZMQ_C_EXAMPLE)

#set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -Wall -O0 -Wno-unused-variable -pthread")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -O0 -pthread")

include_directories(
	/usr/local/zmq-4.3.2/include/
)

link_directories(
	/usr/local/zmq-4.3.2/lib64/
)

set(hwclient_srcs hwclient.c)
set(hwserver_srcs hwserver.c)
set(hwclient3_srcs hwclient3.c)
set(hwserver3_srcs hwserver3.c)

add_executable(hwclient ${hwclient_srcs})
add_executable(hwserver ${hwserver_srcs})
add_executable(hwclient3 ${hwclient3_srcs})
add_executable(hwserver3 ${hwserver3_srcs})

TARGET_LINK_LIBRARIES(hwclient zmq)
TARGET_LINK_LIBRARIES(hwserver zmq)
TARGET_LINK_LIBRARIES(hwclient3 zmq)
TARGET_LINK_LIBRARIES(hwserver3 zmq)