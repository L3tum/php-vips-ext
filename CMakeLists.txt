cmake_minimum_required(VERSION 3.8)
project(vips C)

set(SOURCE_FILES vips.c vips.stub.php php_vips.h)

set(PHP_SOURCE include/php)
set(VIPS_SOURCE include/vips)
set(GLIB_SOURCE include/glib-2.0 include/glib-2.0-2)
message("Using source directory: ${PHP_SOURCE} ${VIPS_SOURCE}")

include_directories(${PHP_SOURCE})
include_directories(${PHP_SOURCE}/main)
include_directories(${PHP_SOURCE}/ext)
include_directories(${PHP_SOURCE}/Zend)
include_directories(${PHP_SOURCE}/TSRM)
include_directories(include)
include_directories(${VIPS_SOURCE})
include_directories(${PROJECT_SOURCE_DIR})
include_directories(${GLIB_SOURCE})

add_library(___ EXCLUDE_FROM_ALL ${SOURCE_FILES})