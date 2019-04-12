workspace(name = "bazel_with_users_node_modules")

# refresh declaration should come in "header" of workspace file, before any loads
refresh(
    roots = ["node_modules"],
    repository = "npm"
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Custom dist of node_modules proto branch
http_archive(
    name = "build_bazel_rules_nodejs",
    strip_prefix = "rules_nodejs-f4f3f65c5a4cfe892086d559e2fb6ec7b3ac4a5a",
    urls = ["https://github.com/gregmagolan/rules_nodejs/archive/f4f3f65c5a4cfe892086d559e2fb6ec7b3ac4a5a.zip"],
)

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories", "npm_install", "yarn_install")

node_repositories()

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
