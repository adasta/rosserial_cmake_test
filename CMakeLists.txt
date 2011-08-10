cmake_minimum_required(VERSION 2.4.6)
include($ENV{ROS_ROOT}/core/rosbuild/rosbuild.cmake)


rosbuild_find_ros_package(rosserial_arduino)
include(${rosserial_arduino_PACKAGE_PATH}/cmake_scripts/rosserial.cmake)
#====================================================================#
#  Chatter                                                           #
#====================================================================#


set(FIRMWARE_NAME chatter)

set(${FIRMWARE_NAME}_BOARD atmega328)               # Arduino Target board
set(${FIRMWARE_NAME}_SRCS # 							Firmware sources
							src/chatter.cpp
							)  
set(${FIRMWARE_NAME}_LIBS )

set(${FIRMWARE_NAME}_PORT /dev/ttyUSB0)            # Serial upload port
generate_ros_firmware(${FIRMWARE_NAME})


#====================================================================#
#  Ultrasound                                                           #
#====================================================================#


set(FIRMWARE_NAME ultrasound)

set(${FIRMWARE_NAME}_BOARD uno)               # Arduino Target board
set(${FIRMWARE_NAME}_SRCS # 							Firmware sources
							src/Ultrasound.cpp
							)  
set(${FIRMWARE_NAME}_LIBS m)

set(${FIRMWARE_NAME}_PORT /dev/ttyUSB0)            # Serial upload port
generate_ros_firmware(${FIRMWARE_NAME})

#====================================================================#
#  Temperature                                                           #
#====================================================================#


set(FIRMWARE_NAME Temperature)

set(${FIRMWARE_NAME}_BOARD atmega328)               # Arduino Target board
set(${FIRMWARE_NAME}_SRCS # 							Firmware sources
							src/Temperature.cpp
							)  
set(${FIRMWARE_NAME}_LIBS m)

set(${FIRMWARE_NAME}_PORT /dev/ttyUSB0)            # Serial upload port
#generate_ros_firmware(${FIRMWARE_NAME})


#====================================================================#
#  Pubsub                                                           #
#====================================================================#


set(FIRMWARE_NAME pubsub)

set(${FIRMWARE_NAME}_BOARD atmega328)               # Arduino Target board
set(${FIRMWARE_NAME}_SRCS # 							Firmware sources
							src/pubsub.cpp
							)  
set(${FIRMWARE_NAME}_LIBS )

set(${FIRMWARE_NAME}_PORT /dev/ttyUSB0)            # Serial upload port
generate_ros_firmware(${FIRMWARE_NAME})

