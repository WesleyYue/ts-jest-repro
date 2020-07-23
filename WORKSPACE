workspace(
    name = "jest_repro",
    managed_directories = {
        "@npm": ["node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "5bf77cc2d13ddf9124f4c1453dd96063774d755d4fc75d922471540d1c9a8ea8",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/2.0.0/rules_nodejs-2.0.0.tar.gz"],
)

# http_archive(
#     name = "build_bazel_rules_nodejs",
#     sha256 = "41b5d9796db19a022bc4a4ca7e9e9f72d92195643ccd875dff325c5e980ee470",
#     urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/2.0.0-rc.3/rules_nodejs-2.0.0-rc.3.tar.gz"],
# )

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
