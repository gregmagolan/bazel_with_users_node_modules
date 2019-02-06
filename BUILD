load("@build_bazel_rules_nodejs//:defs.bzl", "nodejs_binary")

nodejs_binary(
    name = "main",
    entry_point = "bazel_with_users_node_modules/main.js",
    data = [
        "@npm//typescript",
        "main.js",
    ],
)
