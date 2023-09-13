add_executable(stm32-devcontainer-blink-example Main.cpp)
emil_build_for(stm32-devcontainer-blink-example TARGET_MCU_VENDOR st PREREQUISITE_BOOL HALST_BUILD_EXAMPLES)

target_compile_definitions(stm32-devcontainer-blink-example PUBLIC
    NUCLEO=Nucleo64Ui
)

target_link_libraries(stm32-devcontainer-blink-example PRIVATE
    services.util
    hal_st.instantiations
)

halst_target_default_linker_scripts(stm32-devcontainer-blink-example)
halst_target_default_init(stm32-devcontainer-blink-example)

emil_generate_artifacts(TARGET stm32-devcontainer-blink-example LST MAP BIN HEX)
