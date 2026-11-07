file(GLOB UNIT_TESTS "*.cpp")

set(Boost_USE_STATIC_LIBS OFF)

find_package(Boost REQUIRED COMPONENTS unit_test_framework)

add_executable(chainbase_test ${UNIT_TESTS})
target_compile_definitions(chainbase_test PRIVATE BOOST_TEST_DYN_LINK)
target_link_libraries(chainbase_test Boost::unit_test_framework chainbase ${PLATFORM_SPECIFIC_LIBS})
