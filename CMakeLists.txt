cmake_minimum_required(VERSION 3.28)
project(graphon)

# won't work for install
# set(CMAKE_CXX_STANDARD 23)
add_library(graphon graphon_noop_impl.cpp)
target_sources(graphon PUBLIC
	FILE_SET CXX_MODULES FILES graphon.cppm)
target_compile_features(graphon PUBLIC cxx_std_23)

include(GNUInstallDirs)
install(TARGETS graphon
	EXPORT graphon-config DESTINATION ${CMAKE_INSTALL_LIBDIR}/
	FILE_SET CXX_MODULES DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/modules)
	#	CXX_MODULES_BMI DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/graphon)
install(EXPORT graphon-config NAMESPACE graphon:: DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/graphon/)
