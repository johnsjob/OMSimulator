project(OMSimulatorLib)

#set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_INSTALL_RPATH "$ORIGIN/../lib:$ORIGIN/")

IF (CMAKE_COMPILER_IS_GNUCC AND CMAKE_CXX_COMPILER_VERSION VERSION_GREATER 5.1)
  SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Werror=return-local-addr")
  SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Werror=return-type")
ENDIF()

# Export all symbols from the DLL on Windows
IF (WIN32 AND MSVC)
  set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
  add_definitions(-DBOOST_ALL_DYN_LINK)
ENDIF()

list(APPEND OMSIMULATORLIB_SOURCES Clock.cpp)
list(APPEND OMSIMULATORLIB_SOURCES Clocks.cpp)
list(APPEND OMSIMULATORLIB_SOURCES CompositeModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES CSVReader.cpp)
list(APPEND OMSIMULATORLIB_SOURCES CSVWriter.cpp)
list(APPEND OMSIMULATORLIB_SOURCES DirectedGraph.cpp)
list(APPEND OMSIMULATORLIB_SOURCES FMUWrapper.cpp)
list(APPEND OMSIMULATORLIB_SOURCES LookupTable.cpp)
list(APPEND OMSIMULATORLIB_SOURCES MatReader.cpp)
list(APPEND OMSIMULATORLIB_SOURCES MatVer4.cpp)
list(APPEND OMSIMULATORLIB_SOURCES MATWriter.cpp)
list(APPEND OMSIMULATORLIB_SOURCES OMSimulator.cpp)
list(APPEND OMSIMULATORLIB_SOURCES ResultReader.cpp)
list(APPEND OMSIMULATORLIB_SOURCES ResultWriter.cpp)
list(APPEND OMSIMULATORLIB_SOURCES Settings.cpp)
list(APPEND OMSIMULATORLIB_SOURCES Variable.cpp)

list(APPEND OMSIMULATORLIB_SOURCES oms2/CompositeModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ExternalModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/TLMConnection.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/TLMInterface.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ComRef.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Connection.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Connector.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/DirectedGraph.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Element.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/FMICompositeModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/FMISubModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/FMUInfo.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/FMUWrapper.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Logging.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Model.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Scope.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/SignalRef.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Table.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/TLMCompositeModel.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/Variable.cpp)

list(APPEND OMSIMULATORLIB_SOURCES oms2/ssd/ConnectionGeometry.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ssd/ConnectorGeometry.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ssd/ElementGeometry.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ssd/SystemGeometry.cpp)
list(APPEND OMSIMULATORLIB_SOURCES oms2/ssd/Tags.cpp)

list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Plugin/TLMPlugin.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Plugin/PluginImplementer.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Logging/TLMErrorLog.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Communication/TLMCommUtil.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Communication/TLMClientComm.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterface1D.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterface3D.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterface.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterfaceSignal.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterfaceSignalInput.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Interfaces/TLMInterfaceSignalOutput.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/common/Parameters/ComponentParameter.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/coordTransform.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/double3.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/double33.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/double33s.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/dsyevq3.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/dsyevv3.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/dsytrd3.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/dsyevc3.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/ErrorLog.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/tostr.cc)
list(APPEND OMSIMULATORLIB_SOURCES ../../OMTLMSimulator/3rdParty/misc/src/Bstring.cc)

configure_file("${CMAKE_CURRENT_SOURCE_DIR}/Version.cpp.in" "${CMAKE_CURRENT_BINARY_DIR}/Version.cpp" @ONLY)
list(APPEND OMSIMULATORLIB_SOURCES "${CMAKE_CURRENT_BINARY_DIR}/Version.cpp")

include_directories(${FMILibrary_INCLUDEDIR})
include_directories(${CVODELibrary_INCLUDEDIR})
include_directories(${KINSOLLibrary_INCLUDEDIR})
include_directories(${PUGIXML_INCLUDEDIR})
include_directories(${Boost_INCLUDE_DIRS})
include_directories(${OMTLMSIMULATORLIB_INCLUDEDIR})
include_directories(${OMTLMSIMULATOR_INCLUDEDIR})
include_directories(${CTPL_INCLUDEDIR})
include_directories(${OMTLMSIMULATOR_3RDPARTY_INCLUDEDIR})

link_directories(${FMILibrary_LIBRARYDIR})
link_directories(${CVODELibrary_LIBRARYDIR})
link_directories(${KINSOLLibrary_LIBRARYDIR})
link_directories(${Boost_LIBRARY_DIRS})
link_directories(${OMTLMSIMULATORLIB_LIBRARYDIR})

# Shared library version
add_library(OMSimulatorLib_shared SHARED ${OMSIMULATORLIB_SOURCES})
set_target_properties(OMSimulatorLib_shared PROPERTIES OUTPUT_NAME OMSimulatorLib)
IF(WIN32 AND MSVC)
  target_link_libraries(OMSimulatorLib_shared fmilib sundials_kinsol sundials_cvode sundials_nvecserial ${Boost_LIBRARIES} omtlmsimulator wsock32 ws2_32)
ELSEIF (WIN32 AND MINGW)
  target_link_libraries(OMSimulatorLib_shared fmilib shlwapi sundials_kinsol sundials_cvode sundials_nvecserial ${Boost_LIBRARIES} omtlmsimulator wsock32 ws2_32)
ELSE()
  target_link_libraries(OMSimulatorLib_shared fmilib sundials_kinsol sundials_cvode sundials_nvecserial ${Boost_LIBRARIES} omtlmsimulator)
ENDIF()

install(TARGETS OMSimulatorLib_shared DESTINATION lib)
install(TARGETS OMSimulatorLib_shared DESTINATION bin)

# Static library version
add_library(OMSimulatorLib STATIC ${OMSIMULATORLIB_SOURCES})
set_target_properties(OMSimulatorLib PROPERTIES OUTPUT_NAME OMSimulatorLib)
set_target_properties(OMSimulatorLib PROPERTIES POSITION_INDEPENDENT_CODE ON)
install(TARGETS OMSimulatorLib DESTINATION lib)

install(FILES OMSimulator.h Types.h DESTINATION include)
