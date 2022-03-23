## Raspberry-pi-pico

```cma
file(GLOB_RECURSE SRC_DIR_LIST "Src/*.*")

#添加源文件到工程, 将DIR_LIB_SRCS中文件列表以静态库的方式加入工程
target_sources(${PROJECT_NAME} PUBLIC
        ${SRC_DIR_LIST}										#将DIR_LIB_SRCS中文件列表以静态库的方式加入工程
        )

#添加头文件到工程
target_include_directories(${PROJECT_NAME} PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/Inc
        )

#target_link_libraries(${PROJECT_NAME}
#        pico_stdlib
#        )

# 编译后打印占用 ROM, RAM
target_link_options(pico_standard_link INTERFACE "LINKER:--print-memory-usage")
```
