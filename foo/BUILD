load("@protobuf//bazel:proto_library.bzl", "proto_library")
load("@aspect_rules_ts//ts:proto.bzl", "ts_proto_library")
load("@npm//:defs.bzl", "npm_link_all_packages")

package(default_visibility = ["//visibility:public"])

npm_link_all_packages(name = "node_modules")

proto_library(
    name = "foo_proto",
    srcs = [
        "foo.proto",
    ],
    deps = [
        "@my_subproject//bar:bar_proto",
    ],
)

ts_proto_library(
    name = "foo_ts_proto",
    copy_files = False,
    gen_connect_es = False,
    node_modules = ":node_modules",
    proto = ":foo_proto",
    protoc_gen_options = {
        "json_types": "true",
    },
    deps = [
        "@my_subproject//bar:bar_ts_proto",
    ],
)
