# This package contains the build rule to build elemental2-webstorage.

package(
    default_visibility = [
        "//:__subpackages__",
    ],
    # Apache2
    licenses = ["notice"],
)

load("@com_google_jsinterop_generator//:jsinterop_generator.bzl", "jsinterop_generator")

filegroup(
    name = "externs",
    srcs = ["//third_party:webstorage.js"],
)

jsinterop_generator(
    name = "webstorage",
    srcs = [":externs"],
    extension_type_prefix = "WebStorage",
    integer_entities_files = ["integer_entities.txt"],
    # override auto generated js_deps in order not to provide extern files
    # Common extern file are included by default.
    j2cl_js_deps = [],
    deps = [
        "//java/elemental2/core",
        "//java/elemental2/dom",
    ],
)
