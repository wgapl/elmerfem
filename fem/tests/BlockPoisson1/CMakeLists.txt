INCLUDE(${CMAKE_CURRENT_SOURCE_DIR}/../test_macros.cmake)
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

CONFIGURE_FILE( case.sif case.sif COPYONLY)
ADD_ELMERTEST_MODULE(BlockPoisson1 PoissonAssembly PoissonAssembly.f90)

file(COPY ELMERSOLVER_STARTINFO PoissonAssembly.f90 angle.grd DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

ADD_ELMER_TEST(BlockPoisson1)
ADD_ELMER_LABEL(BlockPoisson1 quick)
