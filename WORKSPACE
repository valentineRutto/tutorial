android_sdk_repository(name="androidsdk", api_level = 30, build_tools_version = "30.0.3")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "4.2"
RULES_JVM_EXTERNAL_SHA = "cd1a77b7b02e8e008439ca76fd34f5b07aecb8c752961f9640dea15e9e5ba1ca"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:repositories.bzl", "rules_jvm_external_deps")

rules_jvm_external_deps()

load("@rules_jvm_external//:setup.bzl", "rules_jvm_external_setup")

rules_jvm_external_setup()

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "junit:junit:4.12",
        "androidx.test.espresso:espresso-core:3.1.1",
        "org.hamcrest:hamcrest-library:1.3",
        "com.google.android.material:material:1.0.0-alpha3",
        "androidx.appcompat:appcompat:1.2.0"
# "androidx.core:core:1.0.0",
    ],
    repositories = [
        # Private repositories are supported through HTTP Basic auth

        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)
# Everything below this line is used for the Android testing tools and their dependencies
# ---------------------------------------------------------------------------------------
#   "junit:junit:4.12",
#        "com.google.inject:guice:4.0",
#        "org.hamcrest:java-hamcrest:2.0.0.0",
#        "androidx.test.espresso:espresso-core:3.1.1",
#        "androidx.test:runner:1.1.1",
#        "androidx.test:rules:1.1.1",
#        "androidx.test.ext:junit:1.1.0",
#        "android.arch.lifecycle:common:1.1.1",
#        "android.arch.lifecycle:viewmodel:1.1.1",
# Android Test Support
#
# This repository contains the supporting tools to run Android instrumentation tests,
# like the emulator definitions (android_device) and the device broker/test runner.
#load("@android_test_support//:repo.bzl", "android_test_repositories")

#android_test_repositories()







