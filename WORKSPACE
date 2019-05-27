workspace(
    name = "bazel_with_users_node_modules",
    managed_directories = {"@npm": ["node_modules"]},
)


load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "abcf497e89cfc1d09132adfcd8c07526d026e162ae2cb681dcb896046417ce91",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/0.30.1/rules_nodejs-0.30.1.tar.gz"],
)

load("@build_bazel_rules_nodejs//:defs.bzl", "npm_install", "yarn_install")

# Uncomment the npm install rule to test
# npm_install(
#     name = "npm",
#     package_json = "//:package.json",
#     package_lock_json = "//:package-lock.json",
#     quiet = False,
# )

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
    quiet = False,
)
