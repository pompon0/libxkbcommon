cc_library(
  name = "config",
  hdrs = ["build/config.h"],
  strip_include_prefix = "build",
)

cc_library(
  name = "include",
  hdrs = glob(["include/**/*.h"]),
  strip_include_prefix = "include",
)

cc_library(
  name = "src",
  hdrs = glob(["src/**/*.h"]),
  strip_include_prefix = "src",
)

cc_library(
  name = "src_x11",
  hdrs = glob(["src/x11/*.h"]),
  strip_include_prefix = "src/x11",
)

cc_library(
  name = "src_xkbcomp",
  hdrs = glob(["src/xkbcomp/*.h"]),
  strip_include_prefix = "src/xkbcomp",
)

cc_library(
  name = "parser",
  hdrs = ["build/libxkbcommon.so.0.0.0.p/parser.h"],
  srcs = ["build/libxkbcommon.so.0.0.0.p/parser.c"],
  strip_include_prefix = "build/libxkbcommon.so.0.0.0.p",
  deps = [
    ":config",
    ":src",
  ],
)

cc_library(
  name = "xkbcommon",
  srcs = glob(["src/**/*.c"],exclude=[
    "src/registry.c",
    "src/compose/*.c",
  ]),
  visibility = ["//visibility:public"],
  #TODO: implementation_deps
  deps = [
    ":include",
    ":config",
    ":src",
    ":src_x11",
    ":src_xkbcomp",
    ":parser",
  ],
)

