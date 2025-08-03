load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "onnxruntime_osx_arm64",
    build_file_content = """
cc_import(
    name = "so",
    shared_library = "lib/libonnxruntime.1.22.0.dylib",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "headers",
    srcs = glob(["include/**/*.h"]),
    visibility = ["//visibility:public"],
)
    """,

    sha256 = "cab6dcbd77e7ec775390e7b73a8939d45fec3379b017c7cb74f5b204c1a1cc07",
    strip_prefix = "onnxruntime-osx-arm64-1.22.0",
    urls = ["https://github.com/microsoft/onnxruntime/releases/download/v1.22.1/onnxruntime-osx-arm64-1.22.0.tgz"],
)