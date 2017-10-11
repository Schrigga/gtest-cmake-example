find_package(GTest REQUIRED)

if   (APPLE)
	add_definitions(-DGTEST_USE_OWN_TR1_TUPLE)
	add_definitions(-D__GLIBCXX__)
endif(APPLE)

#############
# Unit Tests
#############

add_executable(runUnitTests test_project1.cpp )

target_link_libraries(runUnitTests GTest::GTest GTest::Main)

target_link_libraries(runUnitTests project1_lib)

add_test (NAME MyTest COMMAND runUnitTests)
