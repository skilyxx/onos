workspace(name = "org_onosproject_onos")

load("//tools/build/bazel:bazel_version.bzl", "check_bazel_version")
check_bazel_version()

load("//tools/build/bazel:generate_workspace.bzl", "generated_maven_jars")
generated_maven_jars()

load("//tools/build/bazel:protobuf_workspace.bzl", "generate_protobuf")
generate_protobuf()

load("//tools/build/bazel:grpc_workspace.bzl", "generate_grpc")
generate_grpc()

load("@io_grpc_grpc_java//:repositories.bzl", "grpc_java_repositories")
grpc_java_repositories(
    omit_javax_annotation = False,

    omit_com_google_api_grpc_google_common_protos = True,
    omit_com_google_errorprone_error_prone_annotations = True,
    omit_com_google_auth_google_auth_library_credentials = True,
    omit_io_opencensus_api = True,
    omit_io_opencensus_grpc_metrics = True,
    omit_com_google_code_findbugs_jsr305 = True,
    omit_com_google_code_gson = True,
    omit_com_google_guava = True,
    omit_com_google_protobuf = True,
    omit_com_google_protobuf_javalite = True,
    omit_com_google_protobuf_nano_protobuf_javanano = True,
    omit_com_google_re2j = True,
    omit_com_google_truth_truth = True,
    omit_com_squareup_okhttp = True,
    omit_com_squareup_okio = True,
    omit_io_netty_buffer = True,
    omit_io_netty_common = True,
    omit_io_netty_transport = True,
    omit_io_netty_codec = True,
    omit_io_netty_codec_socks = True,
    omit_io_netty_codec_http = True,
    omit_io_netty_codec_http2 = True,
    omit_io_netty_handler = True,
    omit_io_netty_handler_proxy = True,
    omit_io_netty_resolver = True,
    omit_io_netty_tcnative_boringssl_static = True,
    omit_junit_junit = True,
    omit_org_apache_commons_lang3 = True
)

load("//tools/build/bazel:p4lang_workspace.bzl", "generate_p4lang")
generate_p4lang()


git_repository(
    name = "build_bazel_rules_nodejs",
    remote = "https://github.com/bazelbuild/rules_nodejs.git",
    tag = "0.10.0", # check for the latest tag when you install
)

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories")
node_repositories(package_json = ["//tools/gui:package.json"])

ONOS_VERSION = "1.14.0-rc2"
