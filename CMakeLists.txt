cmake_minimum_required(VERSION 3.0)

project(bcm2835 VERSION 1.0.0)

# Set source files
set(SOURCES
    src/bcm2835.c
)

# Set header files
set(HEADERS
    src/bcm2835.h
)

# Add library target
add_library(bcm2835 STATIC ${SOURCES} ${HEADERS})

# Set include directories
target_include_directories(bcm2835 PUBLIC include)

# Set library output directory
set_target_properties(bcm2835 PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Set library version
set_target_properties(bcm2835 PROPERTIES
    VERSION ${PROJECT_VERSION}
    SOVERSION ${PROJECT_VERSION_MAJOR}
)