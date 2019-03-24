cmake_minimum_required(VERSION 2.8)
project( camera_calibration )
find_package( OpenCV REQUIRED )
add_executable( camera_calibration camera_calibration.cpp )
target_link_libraries( camera_calibration ${OpenCV_LIBS} ${OpenCV_LIBRARIES} )

#copy dll to bin folder
add_custom_target(CopyFolder 
    COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/dlls"     ${CMAKE_CURRENT_BINARY_DIR}/Release
    COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/dlls"     ${CMAKE_CURRENT_BINARY_DIR}/Debug

   
)