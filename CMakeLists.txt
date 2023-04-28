cmake_minimum_required(VERSION 3.10)
project(hemisphere_v500_msgs VERSION 0.1)

find_package(catkin REQUIRED COMPONENTS
    roscpp
    rospy
    std_msgs
    message_generation
)

add_message_files(FILES
    StampedString.msg
)
generate_messages(DEPENDENCIES std_msgs)

catkin_package(CATKIN_DEPENDS roscpp rospy std_msgs)

catkin_install_python(PROGRAMS python/hemisphere_to_csv.py
                      DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
