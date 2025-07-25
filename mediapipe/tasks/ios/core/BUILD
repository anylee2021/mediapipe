# Copyright 2022 The MediaPipe Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# load("@rules_cc//cc:objc_library.bzl", "objc_library")

package(default_visibility = ["//mediapipe/tasks:internal"])

licenses(["notice"])

objc_library(
    name = "MPPBaseOptions",
    srcs = ["sources/MPPBaseOptions.m"],
    hdrs = ["sources/MPPBaseOptions.h"],
    deps = ["//third_party/apple_frameworks:Foundation"],
)

objc_library(
    name = "MPPTaskOptions",
    srcs = ["sources/MPPTaskOptions.m"],
    hdrs = ["sources/MPPTaskOptions.h"],
    deps = [
        ":MPPBaseOptions",
        "//third_party/apple_frameworks:Foundation",
    ],
)

objc_library(
    name = "MPPTaskResult",
    srcs = ["sources/MPPTaskResult.m"],
    hdrs = ["sources/MPPTaskResult.h"],
    deps = ["//third_party/apple_frameworks:Foundation"],
)

objc_library(
    name = "MPPTaskOptionsProtocol",
    hdrs = ["sources/MPPTaskOptionsProtocol.h"],
    deps = [
        "//mediapipe/framework:calculator_options_cc_proto",
        "//third_party/apple_frameworks:Foundation",
        "@com_google_protobuf//:protobuf",
    ],
)

objc_library(
    name = "MPPTaskInfo",
    srcs = ["sources/MPPTaskInfo.mm"],
    hdrs = ["sources/MPPTaskInfo.h"],
    copts = [
        "-ObjC++",
        "-std=c++20",
        "-Xclang=-fno-cxx-modules",
    ],
    deps = [
        ":MPPTaskOptions",
        ":MPPTaskOptionsProtocol",
        "//mediapipe/calculators/core:flow_limiter_calculator_cc_proto",
        "//mediapipe/framework:calculator_cc_proto",
        "//mediapipe/framework:calculator_options_cc_proto",
        "//mediapipe/tasks/ios/common:MPPCommon",
        "//mediapipe/tasks/ios/common/utils:MPPCommonUtils",
        "//mediapipe/tasks/ios/common/utils:NSStringHelpers",
        "//third_party/apple_frameworks:Foundation",
    ],
)

objc_library(
    name = "MPPTextPacketCreator",
    srcs = ["sources/MPPTextPacketCreator.mm"],
    hdrs = ["sources/MPPTextPacketCreator.h"],
    copts = [
        "-ObjC++",
        "-std=c++20",
        "-Xclang=-fno-cxx-modules",
    ],
    deps = [
        "//mediapipe/framework:packet",
        "//mediapipe/tasks/ios/common/utils:NSStringHelpers",
        "//third_party/apple_frameworks:Foundation",
    ],
)

objc_library(
    name = "MPPTaskRunner",
    srcs = ["sources/MPPTaskRunner.mm"],
    hdrs = ["sources/MPPTaskRunner.h"],
    copts = [
        "-ObjC++",
        "-std=c++20",
        "-Xclang=-fno-cxx-modules",
    ],
    deps = [
        ":MPPTaskInfo",
        "//mediapipe/framework:calculator_cc_proto",
        "//mediapipe/tasks/cc/core:mediapipe_builtin_op_resolver",
        "//mediapipe/tasks/cc/core:task_runner",
        "//mediapipe/tasks/ios/common/utils:MPPCommonUtils",
        "//third_party/apple_frameworks:Foundation",
        "@com_google_protobuf//:protobuf",
    ],
)

objc_library(
    name = "MPPPacketCreator",
    srcs = ["sources/MPPPacketCreator.mm"],
    hdrs = ["sources/MPPPacketCreator.h"],
    copts = [
        "-ObjC++",
        "-std=c++20",
        "-Xclang=-fno-cxx-modules",
    ],
    deps = [
        "//mediapipe/framework:packet",
        "//third_party/apple_frameworks:Foundation",
    ],
)
