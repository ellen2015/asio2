#
# COPYRIGHT (C) 2017-2021, zhllxt
# 
# author   : zhllxt
# email    : 37792738@qq.com
# 
# Distributed under the GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007
# (See accompanying file LICENSE or see <http://www.gnu.org/licenses/>)
#

#GroupSources (asio2 "/")
#GroupSources (asio "/")
#GroupSources (bho "/")

aux_source_directory(. SRC_FILES)

source_group("" FILES ${SRC_FILES})

set(TARGET_NAME asio_tcp_tps_client)

add_executable (
    ${TARGET_NAME}
    ${SRC_FILES}
    ${TARGET_NAME}.cpp
)

set_property(TARGET ${TARGET_NAME} PROPERTY FOLDER "bench/tcp")

#SET_TARGET_PROPERTIES(${TARGET_NAME} PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${ASIO2_EXES_DIR})

set_target_properties(${TARGET_NAME} PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY ${ASIO2_EXES_DIR})

target_link_libraries(${TARGET_NAME} ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(${TARGET_NAME} ${GENERAL_LIBS})

include_directories (${ASIO2_ROOT_DIR}/asio)
