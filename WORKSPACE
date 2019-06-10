workspace(
    name = "bazel_with_users_node_modules",
    managed_directories = {"@npm": ["node_modules"]},
)


load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "e04a82a72146bfbca2d0575947daa60fda1878c8d3a3afe868a8ec39a6b968bb",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/0.31.1/rules_nodejs-0.31.1.tar.gz"],
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
