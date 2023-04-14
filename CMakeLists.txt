idf_build_get_property(components_to_build BUILD_COMPONENTS)

set(src)
set(include)
set(priv_requires)

set(srcs    "src/WebSockets.cpp"
            "src/WebSocketsClient.cpp"
            "src/WebSocketsServer.cpp"
            "src/SocketIOclient.cpp"

            "src/libsha1/libsha1.c"
            )
set(include "src" 
            )

idf_component_register(SRCS "${srcs}"
                       INCLUDE_DIRS ${include}
                       REQUIRES "FEmbed-Arduino FEmbed-Lwip"
                       PRIV_REQUIRES ${priv_requires})

target_compile_options(${COMPONENT_LIB} PRIVATE -DESP32)