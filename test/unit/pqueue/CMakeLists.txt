set(PACKAGE_NAME unit-pqueue)

set(CDSGTEST_PQUEUE_SOURCES
    ../main.cpp
    fcpqueue_boost_stable_vector.cpp
    fcpqueue_deque.cpp
    fcpqueue_vector.cpp
    intrusive_mspqueue.cpp
    mspqueue.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}
)

add_executable(${PACKAGE_NAME} ${CDSGTEST_PQUEUE_SOURCES})
target_link_libraries(${PACKAGE_NAME} 
    ${CDS_SHARED_LIBRARY}
    ${GTEST_LIBRARY}
    ${Boost_THREAD_LIBRARY}
    ${Boost_SYSTEM_LIBRARY}
    ${CMAKE_THREAD_LIBS_INIT}
)

add_test(NAME ${PACKAGE_NAME} COMMAND ${PACKAGE_NAME} WORKING_DIRECTORY ${EXECUTABLE_OUTPUT_PATH})