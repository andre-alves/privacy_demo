
load("@build_bazel_rules_apple//apple:apple.bzl", "local_provisioning_profile")
load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load("@build_bazel_rules_apple//apple:versioning.bzl", "apple_bundle_version")
load("@build_bazel_rules_apple//apple:xcarchive.bzl", "xcarchive")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")

apple_bundle_version(
    name = "version",
    build_version = "0.0.1",
    short_version_string = "1.0",
)

swift_library(
    name = "app.library",
    srcs = glob(["sources/**/*.swift"]),
    module_name = "app",
    deps = [
        "//xcframeworks:Lottie",
    ],
)

ios_application(
    name = "app",
    app_icons = glob(["Assets/Assets.xcassets/AppIcon.appiconset/**"]),
    bundle_id = "com.example.privacydemo",
    bundle_name = "PrivacyDemo",
    executable_name = "PrivacyDemoBinary",
    families = [
        "iphone",
        "ipad",
    ],
    infoplists = [":Info.plist"],
    minimum_os_version = "14.0",
    # provisioning_profile = "app_production_profile",
    version = ":version",
    include_symbols_in_bundle = True,
    visibility = [
        "//visibility:public",
    ],
    deps = [
        ":app.library",
    ],
)

xcarchive(
    name = "app.xcarchive",
    bundle = ":app",
)

local_provisioning_profile(
    name = "app_production_profile",
    profile_name = "match AppStore com.example.privacydemo",
    tags = ["manual"],
    team_id = "1234",
)