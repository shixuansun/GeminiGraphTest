set(BC_FILE_LIST bc.cpp)
set(BFS_FILE_LIST bfs.cpp)
set(CC_FILE_LIST cc.cpp)
set(PR_FILE_LIST pagerank.cpp)
set(SSSP_FILE_LIST sssp.cpp)

add_executable(bc.out ${BC_FILE_LIST})

set(LINK_LIBS ${MPI_LIBRARIES} numa)
target_link_libraries(bc.out ${LINK_LIBS})
add_executable(bfs.out ${BFS_FILE_LIST})
target_link_libraries(bfs.out ${LINK_LIBS})

add_executable(cc.out ${CC_FILE_LIST})
target_link_libraries(cc.out ${LINK_LIBS})

#add_executable(pr.out ${PR_FILE_LIST})
#add_executable(sssp.out ${SSSP_FILE_LIST})