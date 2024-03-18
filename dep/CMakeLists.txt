if(NOT EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/QOlm)
    execute_process(
        COMMAND git clone https://github.com/storyfrom1982/QOlm.git
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        RESULT_VARIABLE result
    )
    if(result)
        message(FATAL_ERROR "Failed to clone QOlm")
    endif()
endif()


if(NOT EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/MaterialDesignSvgo)
    execute_process(
        COMMAND git clone https://github.com/storyfrom1982/MaterialDesignSvgo.git
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        RESULT_VARIABLE result
    )
    if(result)
        message(FATAL_ERROR "Failed to clone MaterialDesignSvgo")
    endif()
endif()


if(NOT EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/QtGeneratorCMake)
    execute_process(
        COMMAND git clone https://github.com/storyfrom1982/QtGeneratorCMake.git
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        RESULT_VARIABLE result
    )
    if(result)
        message(FATAL_ERROR "Failed to clone QtGeneratorCMake")
    endif()
endif()

add_subdirectory(QOlm)
add_subdirectory(QtGeneratorCMake)
set(MATERIALDESIGNICONS_ICONS_DIR "${CMAKE_CURRENT_SOURCE_DIR}/MaterialDesignSvgo/svg" PARENT_SCOPE)
set(MATERIALDESIGNICONS_FONTS_DIR "${CMAKE_CURRENT_SOURCE_DIR}/MaterialDesignSvgo/fonts" PARENT_SCOPE)

