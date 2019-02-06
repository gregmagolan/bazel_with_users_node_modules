workspace(name = "bazel_with_users_node_modules")

# refresh declaration should come in "header" of workspace file, before any loads
refresh(
    roots = ["node_modules"],
    repository = "npm"
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    strip_prefix = "rules_nodejs-badc4ec96d86e94d6259d93fa0399b5ff9d65494",
    urls = ["https://github.com/gregmagolan/rules_nodejs/archive/badc4ec96d86e94d6259d93fa0399b5ff9d65494.zip"],
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
