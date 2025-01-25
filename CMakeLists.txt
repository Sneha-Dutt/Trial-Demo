cmake_minimum_required(VERSION 3.10)
project(AddNumbers)

# Enable testing
enable_testing()

# Add source files
add_executable(main main.cpp add_numbers.cpp)

# Add GoogleTest
find_package(GTest REQUIRED)

# Add test files
add_executable(runTests test_add_numbers.cpp add_numbers.cpp)

# Link GoogleTest libraries
target_link_libraries(runTests GTest::GTest GTest::Main)

# Add tests
add_test(NAME AddNumbersTest COMMAND runTests)
