cmake_minimum_required(VERSION 3.8)

project(robot_arm_assem_v5)

find_package(ament_cmake REQUIRED)

foreach(dir config launch meshes urdf)
    install(
        DIRECTORY ${dir}/
        DESTINATION share/${PROJECT_NAME}/${dir}
    )
endforeach()

ament_package()