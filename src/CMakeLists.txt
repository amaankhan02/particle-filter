file (GLOB HEADER_LIST CONFIGURE_DEPENDS
        "${ParticleFilter_SOURCE_DIR}/include/*.h"
        "${ParticleFilter_SOURCE_DIR}/include/*.hpp")

file (GLOB SOURCE_LIST CONFIGURE_DEPENDS
        "${ParticleFilter_SOURCE_DIR}/src/*.cc"
        "${ParticleFilter_SOURCE_DIR}/src/*.cpp")


# Make an automatic library - will be static or dynamic based on user seting
add_library(pfilter-library ${SOURCE_LIST} ${HEADER_LIST})

# We need this directory, and users of our library will need it too
target_include_directories(pfilter-library PUBLIC ../include)

# all users of this library will need at least c++11
target_compile_features(pfilter-library PUBLIC cxx_std_11)

# IDEs should put the headers in a nice place
source_group(TREE "${PROJECT_SOURCE_DIR}/include" PREFIX "Header Files" FILES ${HEADER_LIST})