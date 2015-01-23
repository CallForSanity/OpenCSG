CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT(OpenCSG)

SET(CPACK_PACKAGE_CONTACT "Patrick Charrier <patrick.charrier@gmail.com>")
INCLUDE(CPack)

# use packages
SET(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")
FIND_PACKAGE(GLEW REQUIRED)
FIND_PACKAGE(GLUT REQUIRED)

# setup directories
SET (CMAKE_LIBRARY_OUTPUT_DIRECTORY
   ${PROJECT_BINARY_DIR}/bin
   CACHE PATH
   "Single Directory for all Libraries"
   )
SET (CMAKE_RUNTIME_OUTPUT_DIRECTORY
   ${PROJECT_BINARY_DIR}/bin
   CACHE PATH
   "Single Directory for all Executables."
   )
SET (CMAKE_ARCHIVE_OUTPUT_DIRECTORY
   ${PROJECT_BINARY_DIR}/lib
   CACHE PATH
   "Single Directory for all static libraries."
   )

# settings
INCLUDE_DIRECTORIES(. include ${GLEW_INCLUDE_DIR} ${GLUT_INCLUDE_DIR})

# build subdirectories
ADD_SUBDIRECTORY(src)
ADD_SUBDIRECTORY(RenderTexture)
ADD_SUBDIRECTORY(example)
