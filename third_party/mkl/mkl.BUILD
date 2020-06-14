licenses(["notice"])  # 3-Clause BSD

exports_files(["license.txt"])

filegroup(
    name = "LICENSE",
    srcs = [
        "license.txt",
    ],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "mkl_headers",
    srcs = glob(["include/*(.cc|.cpp|.cxx|.c++|.C|.c|.h|.hh|.hpp|.ipp|.hxx|.inc|.S|.s|.asm|.a|.lib|.pic.a|.lo|.lo.lib|.pic.lo|.so|.dylib|.dll|.o|.obj|.pic.o)"]),
    includes = ["include"],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "mkl_libs_linux",
    srcs = [
        "lib/libiomp5.so",
        "lib/libmklml_intel.so",
    ],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "mkl_libs_darwin",
    srcs = [
        "lib/libiomp5.dylib",
        "lib/libmklml.dylib",
    ],
    visibility = ["//visibility:public"],
)

cc_import(
    name = "iomp5",
    interface_library = "lib/libiomp5md.lib",
    system_provided = 1,
)

cc_import(
    name = "mklml",
    interface_library = "lib/mklml.lib",
    system_provided = 1,
)

cc_library(
    name = "mkl_libs_windows",
    deps = [
        "iomp5",
        "mklml",
    ],
    linkopts = ["/FORCE:MULTIPLE"],
    visibility = ["//visibility:public"],
)
