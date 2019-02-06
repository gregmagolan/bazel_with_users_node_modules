workspace(name = "bazel_with_users_node_modules")

# refresh declaration should come in "header" of workspace file, before any loads
refresh(
    roots = ["node_modules"],
    repository = "npm"
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# local_repository(
#     name = "build_bazel_rules_nodejs",
#     path = "../rules_nodejs",
# )
http_archive(
    name = "build_bazel_rules_nodejs",
    strip_prefix = "rules_nodejs-0cc179f62af7ecd6607a395315305a32bd4867d7",
    urls = ["https://github.com/gregmagolan/rules_nodejs/archive/0cc179f62af7ecd6607a395315305a32bd4867d7.zip"],
)

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories", "npm_install", "yarn_install")

node_repositories()

# Uncomment the npm install rule to test
# npm_install(
#     name = "npm",
#     package_json = "//:package.json",
#     quiet = False,
# )
yarn_install(
    name = "npm",
    package_json = "//:package.json",
    quiet = False,
)
