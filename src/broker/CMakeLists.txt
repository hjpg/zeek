include(ZeekSubdir)

include_directories(BEFORE
                    ${CMAKE_CURRENT_SOURCE_DIR}
                    ${CMAKE_CURRENT_BINARY_DIR}
)

set(comm_SRCS
    Data.cc
    Manager.cc
    Store.cc
)

bif_target(comm.bif)
bif_target(data.bif)
bif_target(messaging.bif)
bif_target(store.bif)

bro_add_subdir_library(brokercomm ${comm_SRCS})
add_dependencies(bro_brokercomm generate_outputs)
