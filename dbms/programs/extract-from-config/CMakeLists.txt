add_library (clickhouse-extract-from-config-lib ${LINK_MODE} ExtractFromConfig.cpp)
target_link_libraries (clickhouse-extract-from-config-lib PRIVATE clickhouse_common_config clickhouse_common_io ${Boost_PROGRAM_OPTIONS_LIBRARY})

if (CLICKHOUSE_SPLIT_BINARY)
    add_executable (clickhouse-extract-from-config clickhouse-extract-from-config.cpp)
    target_link_libraries (clickhouse-extract-from-config PRIVATE clickhouse-extract-from-config-lib)
endif ()
