WRAP_GGO(rtkdecomposedualenergyprojections_GGO_C rtkdecomposedualenergyprojections.ggo ${RTK_BINARY_DIR}/rtkVersion.ggo)
add_executable(rtkdecomposedualenergyprojections rtkdecomposedualenergyprojections.cxx ${rtkdecomposedualenergyprojections_GGO_C})
target_link_libraries(rtkdecomposedualenergyprojections RTK)

# Installation code
if(NOT RTK_INSTALL_NO_EXECUTABLES)
  foreach(EXE_NAME rtkdecomposedualenergyprojections) 
    install(TARGETS ${EXE_NAME}
      RUNTIME DESTINATION ${RTK_INSTALL_RUNTIME_DIR} COMPONENT Runtime
      LIBRARY DESTINATION ${RTK_INSTALL_LIB_DIR} COMPONENT RuntimeLibraries
      ARCHIVE DESTINATION ${RTK_INSTALL_ARCHIVE_DIR} COMPONENT Development)
  endforeach() 
endif()
