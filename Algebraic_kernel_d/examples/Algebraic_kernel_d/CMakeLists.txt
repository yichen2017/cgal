# Created by the script cgal_create_cmake_script
# This is the CMake script for compiling a CGAL application.


project( Algebraic_kernel_d_Examples )

cmake_minimum_required(VERSION 2.8.11)


find_package(CGAL QUIET COMPONENTS Core MPFI)

if ( CGAL_FOUND )

  include( ${CGAL_USE_FILE} )
  include( CGAL_CreateSingleSourceCGALProgram )
  include( CGAL_VersionUtils )

  include_directories (BEFORE ../../include)

  create_single_source_cgal_program( "Compare_1.cpp" )
  create_single_source_cgal_program( "Construct_algebraic_real_1.cpp" )
  create_single_source_cgal_program( "Isolate_1.cpp" )
  create_single_source_cgal_program( "Sign_at_1.cpp" )
  create_single_source_cgal_program( "Solve_1.cpp" )

else()
  
    message(STATUS "This program requires the CGAL library, and will not be compiled.")
  
endif()

