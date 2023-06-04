cmake_minimum_required(VERSION 3.13)

set(PROJECT_NAME "cryptopp")
add_library(${PROJECT_NAME} STATIC IMPORTED GLOBAL)


if(MINGW32)
    set_property(TARGET ${PROJECT_NAME} PROPERTY
    IMPORTED_LOCATION ${CMAKE_CURRENT_BINARY_DIR}/lib/GNU_MinGW/libcryptopp.a)
else()
    set_property(TARGET ${PROJECT_NAME} PROPERTY
    IMPORTED_LOCATION ${CMAKE_CURRENT_BINARY_DIR}/lib/GNU/libcryptopp.a)
endif()

target_include_directories(${PROJECT_NAME} INTERFACE ${CMAKE_CURRENT_BINARY_DIR}/include)
