load("@rules_java//java:defs.bzl", "java_library", "java_test")
load("//scala:scala.bzl", "scala_library", "scala_test")
load("//scala:scala_toolchain.bzl", "scala_toolchain")

scala_toolchain(
    name = "enable_code_coverage_aspect_impl",
    enable_code_coverage_aspect = "on",
    visibility = ["//visibility:public"],
)

toolchain(
    name = "enable_code_coverage_aspect",
    toolchain = "enable_code_coverage_aspect_impl",
    toolchain_type = "@io_bazel_rules_scala//scala:toolchain_type",
    visibility = ["//visibility:public"],
)

scala_test(
    name = "test-all",
    srcs = [
        "TestAll.scala",
    ],
    deps = [
        ":a1",
        ":a2",
        ":b1",
    ],
)

java_test(
    name = "test-b2",
    srcs = [
        "TestB2.java",
    ],
    tags = ["manual"],
    test_class = "TestB2",
    deps = [
        ":b2",
    ],
)

scala_library(
    name = "a1",
    srcs = [
        "A1.scala",
    ],
    deps = [
        ":b1",
    ],
)

scala_library(
    name = "b1",
    srcs = [
        "B1.scala",
    ],
)

scala_library(
    name = "a2",
    srcs = [
        "A2.scala",
    ],
    deps = [
        ":b2",
    ],
)

java_library(
    name = "b2",
    srcs = [
        "B2.java",
    ],
    deps = [
        ":c2",
    ],
)

scala_library(
    name = "c2",
    srcs = [
        "C2.scala",
    ],
)
