add_executable(ParticleFilterApp main.cpp)
target_compile_features(ParticleFilterApp PRIVATE cxx_std_14)
target_link_libraries(ParticleFilterApp PRIVATE pfilter-library)