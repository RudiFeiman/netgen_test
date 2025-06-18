cmake_minimum_required(VERSION 3.20)
project(NETGEN_Test)

#set(USE_TEST 1)

if(USE_TEST)
enable_testing()
endif()

#set(CMAKE_CONFIGURATION_TYPES "Debug;Release")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SOURCE_FILES 
    ng_occ.cpp)
add_executable(${PROJECT_NAME} ${SOURCE_FILES})

SET(OpenCASCADE_LIBS 
  TKBin
  TKBinL
  TKBinTObj
  TKBinXCAF
  TKBO
  TKBool
  TKBRep
  TKCAF
  TKCDF
  TKDCAF
  TKDE
  TKDECascade
  TKDEGLTF
  TKDEIGES
  TKDEOBJ
  TKDEPLY
  TKDESTEP
  TKDESTL
  TKDEVRML
  TKDraw
  TKernel
  TKExpress
  TKFeat
  TKFillet
  TKG2d
  TKG3d
  TKGeomAlgo
  TKGeomBase
  TKHLR
#TKIVtk
#TKIVtkDraw
  TKLCAF
  TKMath
  TKMesh
  TKMeshVS
  TKOffset
  TKOpenGl
  TKPrim
  TKQADraw
  TKRWMesh
  TKService
  TKShHealing
  TKStd
  TKStdL
  TKTObj
  TKTObjDRAW
  TKTopAlgo
  TKTopTest
  TKV3d
  TKVCAF
  TKViewerTest
  TKXCAF
  TKXDEDRAW
  TKXMesh
  TKXml
  TKXmlL
  TKXmlTObj
  TKXmlXCAF
  TKXSBase
  TKXSDRAW
  TKXSDRAWDE
  TKXSDRAWGLTF
  TKXSDRAWIGES
  TKXSDRAWOBJ
  TKXSDRAWPLY
  TKXSDRAWSTEP
  TKXSDRAWSTL
  TKXSDRAWVRML
)

include_directories(
  ../../../Win/Netgen/v6.2.2404/m_install/include
  ../../../Win/OpenCASCADE/v7.9.0_Dev/install/inc
  ../../../Win/zlib/v1.3.1/install_release/include
  ../../../Win/Tcltk/m_install/include
  ../../../Win/pybind11/v2.13.6/m_install/include
)

target_link_directories(${PROJECT_NAME} PRIVATE
  ../../../Win/Netgen/v6.2.2404/m_install/lib
  ../../../Win/OpenCASCADE/v7.9.0_Dev/install/win64/vc14/lib
  ../../../Win/zlib/v1.3.1/install_release/lib
  ../../../Win/Tcltk/m_install/lib
)

target_link_libraries(${PROJECT_NAME} PRIVATE zlib nglib ngcore ${OpenCASCADE_LIBS})