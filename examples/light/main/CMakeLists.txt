idf_component_register(SRC_DIRS          "."
                       PRIV_INCLUDE_DIRS  "." "${ESP_MATTER_PATH}/examples/common/utils")

                       include("${MATTER_SDK_PATH}/src/app/codegen-data-model-provider/model.cmake")
                       target_sources(${COMPONENT_LIB} PRIVATE ${CODEGEN_DATA_MODEL_SOURCES}
                                                               "${MATTER_SDK_PATH}/src/app/util/ember-global-attribute-access-interface.cpp")

set_property(TARGET ${COMPONENT_LIB} PROPERTY CXX_STANDARD 17)
target_compile_options(${COMPONENT_LIB} PRIVATE "-DCHIP_HAVE_CONFIG_H")
