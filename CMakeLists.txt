cmake_minimum_required(VERSION 3.10)
project(ublox_dgnss)

set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} ${CMAKE_SOURCE_DIR}/ublox_ubx_msgs ${CMAKE_SOURCE_DIR}/ublox_ubx_interfaces ${CMAKE_SOURCE_DIR}/ntrip_client_node ${CMAKE_SOURCE_DIR}/ublox_nav_sat_fix_hp_node ${CMAKE_SOURCE_DIR}/ublox_dgnss_node)

add_subdirectory(ntrip_client_node)
add_subdirectory(ublox_ubx_interfaces)
add_subdirectory(ublox_ubx_msgs)



add_subdirectory(ublox_nav_sat_fix_hp_node)
add_subdirectory(ublox_dgnss_node)
add_subdirectory(ublox_dgnss)




add_dependencies(ublox_dgnss_node ublox_ubx_msgs ublox_ubx_interfaces)
add_dependencies(ublox_nav_sat_fix_hp_node ublox_ubx_msgs ublox_ubx_interfaces)
add_dependencies(ublox_dgnss ublox_dgnss_msgs ublox_ubx_interfaces ublox_dgnss_node ublox_nav_sat_fix_hp_node ntrip_client_node)
