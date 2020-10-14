workspace(
    name = "test",
    managed_directories = {"@npm": ["node_modules"]},
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "fabce5d60b996087d29bc44cf1d5bc44017a92d230114f32b3fc4dc242e73a54",
    strip_prefix = "rules_nodejs-af9feb4f658d9ed6300eb5296cdd3f86038f6201",
    urls = [
        "https://github.com/bazelbuild/rules_nodejs/archive/af9feb4f658d9ed6300eb5296cdd3f86038f6201.tar.gz",
    ],
)

load("@build_bazel_rules_nodejs//:package.bzl", "rules_nodejs_dev_dependencies")

rules_nodejs_dev_dependencies()

load("@build_bazel_rules_nodejs//:index.bzl", "yarn_install")

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

load("@build_bazel_rules_typescript//:package.bzl", "rules_typescript_dev_dependencies")

rules_typescript_dev_dependencies()
