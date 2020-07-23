workspace(
    name = "jest_repro",
    managed_directories = {
        "@npm": ["node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "aa0b0a71afd4e1f203b7092c3284a6606a5bfac77e0bd31f071b37bcac0f7cf3",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/2.0.0-rc.1/rules_nodejs-2.0.0-rc.1.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

yarn_install(
    name = "npm",
    # args = [
    #     "--frozen-lockfile",
    # ],
    data = [
    ],
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

node_repositories(package_json = ["//:package.json"])
