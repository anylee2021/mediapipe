# Copyright 2019, 2021 The MediaPipe Authors.
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

load("//mediapipe/framework/port:build_config.bzl", "mediapipe_cc_proto_library")

# load("@rules_cc//cc:cc_binary.bzl", "cc_binary")
# load("@rules_cc//cc:cc_library.bzl", "cc_library")
# load("@rules_cc//cc:cc_test.bzl", "cc_test")
# Placeholder: load py_proto_library
# Placeholder: load proto_library

licenses(["notice"])

package(default_visibility = ["//visibility:private"])

proto_library(
    name = "mfcc_mel_calculators_proto",
    srcs = ["mfcc_mel_calculators.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "mfcc_mel_calculators_cc_proto",
    srcs = ["mfcc_mel_calculators.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":mfcc_mel_calculators_proto"],
)

proto_library(
    name = "rational_factor_resample_calculator_proto",
    srcs = ["rational_factor_resample_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "rational_factor_resample_calculator_cc_proto",
    srcs = ["rational_factor_resample_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":rational_factor_resample_calculator_proto"],
)

proto_library(
    name = "resample_time_series_calculator_proto",
    srcs = ["resample_time_series_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "resample_time_series_calculator_cc_proto",
    srcs = ["resample_time_series_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":resample_time_series_calculator_proto"],
)

proto_library(
    name = "spectrogram_calculator_proto",
    srcs = ["spectrogram_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = ["//mediapipe/framework:calculator_proto"],
)

mediapipe_cc_proto_library(
    name = "spectrogram_calculator_cc_proto",
    srcs = ["spectrogram_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":spectrogram_calculator_proto"],
)

proto_library(
    name = "stabilized_log_calculator_proto",
    srcs = ["stabilized_log_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "stabilized_log_calculator_cc_proto",
    srcs = ["stabilized_log_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":stabilized_log_calculator_proto"],
)

proto_library(
    name = "time_series_framer_calculator_proto",
    srcs = ["time_series_framer_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "time_series_framer_calculator_cc_proto",
    srcs = ["time_series_framer_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":time_series_framer_calculator_proto"],
)

cc_library(
    name = "audio_decoder_calculator",
    srcs = ["audio_decoder_calculator.cc"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/port:logging",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:audio_decoder",
        "//mediapipe/util:audio_decoder_cc_proto",
    ],
    alwayslink = 1,
)

cc_library(
    name = "basic_time_series_calculators",
    srcs = ["basic_time_series_calculators.cc"],
    hdrs = ["basic_time_series_calculators.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:ret_check",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/strings",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "mfcc_mel_calculators",
    srcs = ["mfcc_mel_calculators.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":mfcc_mel_calculators_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:logging",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_check",
        "@com_google_absl//absl/strings",
        "@com_google_audio_tools//audio/dsp/mfcc",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "rational_factor_resample_calculator",
    srcs = ["rational_factor_resample_calculator.cc"],
    hdrs = ["rational_factor_resample_calculator.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":rational_factor_resample_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:integral_types",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_check",
        "@com_google_absl//absl/log:absl_log",
        "@com_google_absl//absl/strings",
        "@com_google_audio_tools//audio/dsp:resampler",
        "@com_google_audio_tools//audio/dsp:resampler_q",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "resample_time_series_calculator",
    srcs = ["resample_time_series_calculator.cc"],
    hdrs = ["resample_time_series_calculator.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":resample_time_series_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:packet",
        "//mediapipe/framework:timestamp",
        "//mediapipe/framework/api2:contract",
        "//mediapipe/framework/api2:node",
        "//mediapipe/framework/api2:packet",
        "//mediapipe/framework/api2:port",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:ret_check",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_check",
        "@com_google_absl//absl/status",
        "@com_google_audio_tools//audio/dsp:resampler_q",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "stabilized_log_calculator",
    srcs = ["stabilized_log_calculator.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":stabilized_log_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:core_proto",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_check",
    ],
    alwayslink = 1,
)

cc_library(
    name = "spectrogram_calculator",
    srcs = ["spectrogram_calculator.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":spectrogram_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/port:logging",
        "//mediapipe/framework/port:ret_check",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings",
        "@com_google_audio_tools//audio/dsp:window_functions",
        "@com_google_audio_tools//audio/dsp/spectrogram",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_library(
    name = "time_series_framer_calculator",
    srcs = ["time_series_framer_calculator.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":time_series_framer_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:timestamp",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:ret_check",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_check",
        "@com_google_audio_tools//audio/dsp:window_functions",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

proto_library(
    name = "two_tap_fir_filter_calculator_proto",
    srcs = ["two_tap_fir_filter_calculator.proto"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/framework:calculator_proto",
    ],
)

mediapipe_cc_proto_library(
    name = "two_tap_fir_filter_calculator_cc_proto",
    srcs = ["two_tap_fir_filter_calculator.proto"],
    cc_deps = ["//mediapipe/framework:calculator_cc_proto"],
    visibility = ["//visibility:public"],
    deps = [":two_tap_fir_filter_calculator_proto"],
)

cc_library(
    name = "two_tap_fir_filter_calculator",
    srcs = ["two_tap_fir_filter_calculator.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":stabilized_log_calculator_cc_proto",
        ":two_tap_fir_filter_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/api2:node",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/status",
        "@com_google_audio_tools//audio/linear_filters:two_tap_fir_filter",
        "@eigen//:eigen3",
    ],
    alwayslink = 1,
)

cc_test(
    name = "two_tap_fir_filter_calculator_test",
    srcs = ["two_tap_fir_filter_calculator_test.cc"],
    deps = [
        ":two_tap_fir_filter_calculator",
        ":two_tap_fir_filter_calculator_cc_proto",
        "//mediapipe/framework:calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework:output_stream_poller",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:benchmark",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:parse_text_proto",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_test_util",
        "@com_google_absl//absl/log:absl_log",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings",
        "@com_google_audio_tools//audio/dsp:number_util",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "audio_decoder_calculator_test",
    srcs = ["audio_decoder_calculator_test.cc"],
    data = ["//mediapipe/calculators/audio/testdata:test_audios"],
    deps = [
        ":audio_decoder_calculator",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/deps:file_path",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:parse_text_proto",
        "//mediapipe/framework/tool:test_util",
        "@com_google_absl//absl/flags:flag",
    ],
)

cc_test(
    name = "basic_time_series_calculators_test",
    srcs = ["basic_time_series_calculators_test.cc"],
    deps = [
        ":basic_time_series_calculators",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:integral_types",
        "//mediapipe/framework/port:parse_text_proto",
        "//mediapipe/util:time_series_test_util",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "mfcc_mel_calculators_test",
    srcs = ["mfcc_mel_calculators_test.cc"],
    deps = [
        ":mfcc_mel_calculators",
        ":mfcc_mel_calculators_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_test_util",
        "@com_google_audio_tools//audio/dsp/mfcc",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "spectrogram_calculator_test",
    srcs = ["spectrogram_calculator_test.cc"],
    deps = [
        ":spectrogram_calculator",
        ":spectrogram_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:benchmark",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/util:time_series_test_util",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_log",
        "@com_google_absl//absl/status",
        "@com_google_audio_tools//audio/dsp:number_util",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "stabilized_log_calculator_test",
    srcs = ["stabilized_log_calculator_test.cc"],
    deps = [
        ":stabilized_log_calculator",
        ":stabilized_log_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:integral_types",
        "//mediapipe/framework/port:status",
        "//mediapipe/util:time_series_test_util",
        "@eigen//:eigen3",
    ],
)

cc_binary(
    name = "time_series_framer_calculator_benchmark",
    srcs = ["time_series_framer_calculator_benchmark.cc"],
    deps = [
        ":time_series_framer_calculator",
        ":time_series_framer_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:packet",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "@com_google_absl//absl/log:absl_check",
        "@com_google_benchmark//:benchmark",
    ],
)

cc_test(
    name = "time_series_framer_calculator_test",
    srcs = ["time_series_framer_calculator_test.cc"],
    deps = [
        ":time_series_framer_calculator",
        ":time_series_framer_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/util:time_series_test_util",
        "//mediapipe/util:time_series_util",
        "@com_google_absl//absl/log:absl_log",
        "@com_google_absl//absl/status",
        "@com_google_audio_tools//audio/dsp:window_functions",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "rational_factor_resample_calculator_test",
    srcs = ["rational_factor_resample_calculator_test.cc"],
    deps = [
        ":rational_factor_resample_calculator",
        ":rational_factor_resample_calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/framework/port:status",
        "//mediapipe/framework/tool:validate_type",
        "//mediapipe/util:time_series_test_util",
        "@com_google_audio_tools//audio/dsp:resampler",
        "@com_google_audio_tools//audio/dsp:resampler_q",
        "@com_google_audio_tools//audio/dsp:signal_vector_util",
        "@eigen//:eigen3",
    ],
)

cc_test(
    name = "resample_time_series_calculator_test",
    srcs = ["resample_time_series_calculator_test.cc"],
    deps = [
        ":resample_time_series_calculator",
        ":resample_time_series_calculator_cc_proto",
        "//mediapipe/framework:calculator_runner",
        "//mediapipe/framework:packet",
        "//mediapipe/framework:timestamp",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/framework/formats:time_series_header_cc_proto",
        "//mediapipe/framework/port:gtest_main",
        "//mediapipe/util:time_series_test_util",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/types:span",
        "@com_google_audio_tools//audio/dsp:resampler_q",
        "@eigen//:eigen3",
    ],
)
