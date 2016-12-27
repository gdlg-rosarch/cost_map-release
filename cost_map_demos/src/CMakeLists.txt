##############################################################################
# Subdirectories
##############################################################################

add_subdirectory(lib)
add_subdirectory(applications)

if(CATKIN_ENABLE_TESTING)
  add_subdirectory(test)
endif()
