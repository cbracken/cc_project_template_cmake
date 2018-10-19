add_definitions(-std=c++17)

set(CXX_FLAGS
  "-Weverything"
  "-Wno-c++98-compat"
)

set(CXX_TEST_FLAGS
  ${CXX_FLAGS}
  "-Wno-global-constructors"
)

set(LIBFOO_SRCS
  foo.h
  foo.cc
  bar.h
  bar.cc
)

add_executable(main
  main.cc
  ${LIBFOO_SRCS}
)
target_compile_options(main PRIVATE ${CXX_FLAGS})

set(LIBFOO_TEST_SRCS
  foo_test.cc
  bar_test.cc
)

add_executable(libfoo_tests
  ${LIBFOO_SRCS}
  ${LIBFOO_TEST_SRCS}
)
target_link_libraries(libfoo_tests
  gtest
  gtest_main
)
target_compile_options(libfoo_tests PRIVATE ${CXX_TEST_FLAGS})

