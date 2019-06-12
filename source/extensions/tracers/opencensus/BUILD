licenses(["notice"])  # Apache 2

# Trace driver for OpenCensus: https://opencensus.io/

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

envoy_package()

envoy_cc_library(
    name = "config",
    srcs = ["config.cc"],
    hdrs = ["config.h"],
    deps = [
        ":opencensus_tracer_impl",
        "//source/extensions/tracers:well_known_names",
        "//source/extensions/tracers/common:factory_base_lib",
    ],
)

envoy_cc_library(
    name = "opencensus_tracer_impl",
    srcs = ["opencensus_tracer_impl.cc"],
    hdrs = ["opencensus_tracer_impl.h"],
    external_deps = [
        "opencensus_trace",
        "opencensus_trace_cloud_trace_context",
        "opencensus_trace_grpc_trace_bin",
        "opencensus_trace_trace_context",
        "opencensus_exporter_stdout",
        "opencensus_exporter_stackdriver",
        "opencensus_exporter_zipkin",
    ],
    deps = [
        "//source/common/config:utility_lib",
        "//source/common/tracing:http_tracer_lib",
    ],
)