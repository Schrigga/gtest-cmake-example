set( CXX_SOURCES
	main.cpp
   )

add_executable(project1 ${CXX_SOURCES})
target_link_libraries(project1 project1_lib)
