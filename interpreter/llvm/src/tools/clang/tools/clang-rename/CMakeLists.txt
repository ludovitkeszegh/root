set(LLVM_LINK_COMPONENTS
  Option
  Support
  )

add_clang_executable(clang-rename ClangRename.cpp)

target_link_libraries(clang-rename
  clangBasic
  clangFrontend
  clangRewrite
  clangTooling
  clangToolingCore
  clangToolingRefactor
  )

install(TARGETS clang-rename RUNTIME DESTINATION bin)

install(PROGRAMS clang-rename.py
  DESTINATION share/clang
  COMPONENT clang-rename)
install(PROGRAMS clang-rename.el
  DESTINATION share/clang
  COMPONENT clang-rename)
