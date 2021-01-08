cmake_minimum_required(VERSION 3.16)
project(oci8_mod C)

set(PHP_SOURCE "/home/ilya/php-7.4.14")
set(CMAKE_C_STANDARD 99)
add_compile_definitions(HAVE_CONFIG_H)

set(SourcesList "oci8.c" "oci8_collection.c" "oci8_failover.c" "oci8_interface.c" "oci8_lob.c" "oci8_statement.c")

include_directories(${PROJECT_SOURCE_DIR})
include_directories(${PHP_SOURCE})
include_directories(${PHP_SOURCE}/main)
include_directories(${PHP_SOURCE}/Zend)
include_directories(${PHP_SOURCE}/TSRM)
include_directories(${PHP_SOURCE}/ext)
include_directories(${PHP_SOURCE}/sapi)
include_directories(/home/ilya/instantclient_19_8/sdk/include)


add_library(oci8_mod SHARED ${SourcesList})
set_target_properties(oci8_mod PROPERTIES PREFIX "")
set_target_properties(oci8_mod PROPERTIES OUTPUT_NAME "oci8")