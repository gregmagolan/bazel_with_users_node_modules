load("@build_bazel_rules_nodejs//:defs.bzl", "nodejs_test")

nodejs_test(
    name = "main",
    entry_point = ":main.js",
    data = [
        "@npm//typescript",
    ],
)
