licenses(["notice"])  # Apache 2

# Stats sink for the DataDog (https://www.datadoghq.com/) variant of the statsd protocol
# (https://docs.datadoghq.com/developers/dogstatsd/).

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_extension",
    "envoy_package",
)

envoy_package()

envoy_cc_extension(
    name = "config",
    srcs = ["config.cc"],
    hdrs = ["config.h"],
    security_posture = "data_plane_agnostic",
    deps = [
        "//include/envoy/registry",
        "//source/common/network:address_lib",
        "//source/common/network:resolver_lib",
        "//source/extensions/stat_sinks:well_known_names",
        "//source/extensions/stat_sinks/common/statsd:statsd_lib",
        "//source/server:configuration_lib",
        "@envoy_api//envoy/config/metrics/v3alpha:pkg_cc_proto",
    ],
)
