cmake_minimum_required(VERSION 2.8.3)


if(MSVC)
    set(CMAKE_CXX_FLAGS_RELEASE "/Z7")
    set(CMAKE_EXE_LINKER_FLAGS_RELEASE "/INCREMENTAL:NO /DEBUG /OPT:REF /OPT:ICF")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4100 /wd4127 /wd4150 /wd4191 /wd4242 /wd4244 /wd4251 /wd4305 /wd4365 /wd4512 /wd4514 /wd4548 /wd4571 /wd4619 /wd4625 /wd4626 /wd4628 /wd4668 /wd4710 /wd4711 /wd4738 /wd4820 /wd4946 /wd4986 /wd4819 /wd4996 /wd4267")
    add_definitions(-DNDEBUG)
	add_definitions(-D_USE_MATH_DEFINES)
	add_definitions(-DNOMINMAX)
endif()

INCLUDE_DIRECTORIES(${K4A_INCLUDE_DIRS})
INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIR})
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR})
add_executable(OpenTwoKinect "Source_2.cpp" "../Util.cpp" "../StaticImageProperties.cpp")
target_link_libraries(OpenTwoKinect ${OpenCV_LIBS} ${K4A_LIBS})