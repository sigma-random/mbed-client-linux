if(TARGET_LIKE_LINUX)
include("../includes.txt")
add_executable(m2mtimerpimpl_linux
        "../../../../source/m2mtimerpimpl.cpp"
        "main.cpp"
        "m2mtimerpimpl_linuxtest.cpp"
        "test_m2mtimerpimpl_linux.cpp"
        "../stub/common_stub.cpp"
        "../stub/m2mstring_stub.cpp"
)

target_link_libraries(m2mtimerpimpl_linux
    CppUTest
    CppUTestExt
)
set_target_properties(m2mtimerpimpl_linux
PROPERTIES COMPILE_FLAGS "${UTEST_COMPILE_FLAGS}"
           LINK_FLAGS "${UTEST_LINK_FLAGS}")
set(binary "m2mtimerpimpl_linux -ojunit")
add_test(m2mtimerpimpl_linux ${binary})

endif()
