load("//go:def.bzl", "go_binary")
load("//proto:go_proto_library.bzl", "go_proto_library")

go_proto_library(
    name = "my_svc_proto",
    srcs = ["my_svc.proto"],
    has_services = 1,
    deps = [
        "//examples/proto/lib:lib_proto",
        "@com_github_golang_protobuf//ptypes/any:go_default_library",
        "@com_github_golang_protobuf//ptypes/empty:go_default_library",
    ],
)

go_binary(
    name = "test_grpc",
    srcs = ["main.go"],
    deps = [
        ":my_svc_proto",
        "//examples/proto/lib:lib_proto",
        "@com_github_golang_protobuf//ptypes/any:go_default_library",
        "@com_github_golang_protobuf//ptypes/empty:go_default_library",
        "@org_golang_google_grpc//:go_default_library",
        "@org_golang_x_net//context:go_default_library",
    ],
)
