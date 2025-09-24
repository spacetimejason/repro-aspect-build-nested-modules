load("@protobuf//bazel:proto_library.bzl", "proto_library")
load("@aspect_rules_ts//ts:proto.bzl", "ts_proto_library")
load("@npm//:defs.bzl", "npm_link_all_packages")

package(default_visibility = ["//visibility:public"])

npm_link_all_packages(name = "node_modules")

proto_library(
    name = "bar_proto",
    srcs = [
        "bar.proto",
    ],
)

ts_proto_library(
    name = "bar_ts_proto",
    copy_files = False,
    gen_connect_es = False,
    node_modules = ":node_modules",
    proto = ":bar_proto",
    protoc_gen_options = {
        "json_types": "true",
    },
)
