set(RUBY_WRAPPER_SRC
    ../../ext/symengine/ruby_basic.c
    ../../ext/symengine/symengine.c
    )

include_directories(BEFORE ${symengine_BINARY_DIR}/src/ruby/ext/symengine)

add_library(symengine_ruby SHARED ${RUBY_WRAPPER_SRC})
target_link_libraries(symengine_ruby symengine)
set_target_properties(symengine_ruby PROPERTIES PREFIX "" OUTPUT_NAME "symengine")
