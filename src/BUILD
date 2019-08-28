# Convention:
# A java_proto_library that wraps a proto_library named foo_proto
# should be called foo_java_proto.
#
# Note that you only need a java_proto_library for the protos
# you directly use in your code - a java_proto_library converts
# an entire proto graph.
#java_proto_library(
#    name = "person_java_proto",
#    deps = [":person_proto"],
#)

# Convention:
# A java_lite_proto_library that wraps a proto_library named foo_proto
# should be called foo_java_proto_lite.
#java_lite_proto_library(
#    name = "person_java_proto_lite",
#    deps = [":person_proto"],
#)

# Convention:
# A cc_proto_library that wraps a proto_library named foo_proto
# should be called foo_cc_proto.


# load("@com_github_grpc_grpc//bazel:grpc_build_system.bzl", "grpc_proto_library")
load("@com_github_grpc_grpc//bazel:cc_grpc_library.bzl", "cc_grpc_library")

##grpc_proto_library(
cc_grpc_library(
     name = "person_grpc_proto",
     srcs = ["person.proto"],
     deps = [
        ":address_grpc_proto",
    ],
     proto_only = False,
     well_known_protos = False
)

##grpc_proto_library(
cc_grpc_library(
     name = "address_grpc_proto",
     srcs = ["address.proto"],
     deps = [
        ":zip_code_grpc_proto"
    ],
     proto_only = True,
     well_known_protos = False
)

#grpc_proto_library(
cc_grpc_library(
     name = "zip_code_grpc_proto",
     srcs = ["zip_code.proto"],
     deps = [
    ],
     proto_only = True,
     well_known_protos = False
)

#cc_proto_library(
#    name = "person_cc_proto",
#    deps = [":person_proto"],
#)

# Conventions:
# 1. One proto_library rule per .proto file.
# 2. A file named foo.proto will be in a rule named foo_proto.
#proto_library(
#    name = "person_proto",
#    srcs = ["person.proto"],
#    deps = [
#        ":address_proto",
#        # Well known protos should be included as deps in the
#        # proto_library rules of the source files importing them.
#        # A list of all @com_google_protobuf well known protos can
#        # seen with:
#        # `bazel query 'kind(proto_library, @com_google_protobuf//:all)'`
#        "@com_google_protobuf//:any_proto",
#    ],
#)
#
#proto_library(
#    name = "address_proto",
#    srcs = ["address.proto"],
#    deps = [":zip_code_proto"],
#)
#
#proto_library(
#    name = "zip_code_proto",
#    srcs = ["zip_code.proto"],
#)
