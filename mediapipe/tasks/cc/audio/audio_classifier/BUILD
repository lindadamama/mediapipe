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

# load("@rules_cc//cc:cc_library.bzl", "cc_library")
# load("@rules_cc//cc:cc_test.bzl", "cc_test")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])

# Docs for Mediapipe Tasks Audio Classifier
# https://developers.google.com/mediapipe/solutions/audio/audio_classifier
cc_library(
    name = "audio_classifier",
    srcs = ["audio_classifier.cc"],
    hdrs = ["audio_classifier.h"],
    deps = [
        ":audio_classifier_graph",
        "//mediapipe/framework/api2:builder",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/tasks/cc/audio/audio_classifier/proto:audio_classifier_graph_options_cc_proto",
        "//mediapipe/tasks/cc/audio/core:audio_task_api_factory",
        "//mediapipe/tasks/cc/audio/core:base_audio_task_api",
        "//mediapipe/tasks/cc/audio/core:running_mode",
        "//mediapipe/tasks/cc/components/containers:classification_result",
        "//mediapipe/tasks/cc/components/containers/proto:classifications_cc_proto",
        "//mediapipe/tasks/cc/components/processors:classifier_options",
        "//mediapipe/tasks/cc/components/processors/proto:classifier_options_cc_proto",
        "//mediapipe/tasks/cc/core:base_options",
        "//mediapipe/tasks/cc/core:task_runner",
        "//mediapipe/tasks/cc/core/proto:inference_subgraph_cc_proto",
        "@com_google_absl//absl/status:statusor",
        "@org_tensorflow//tensorflow/lite/core/api:op_resolver",
    ],
)

cc_library(
    name = "audio_classifier_graph",
    srcs = ["audio_classifier_graph.cc"],
    deps = [
        "//mediapipe/calculators/audio:time_series_framer_calculator",
        "//mediapipe/calculators/core:constant_side_packet_calculator",
        "//mediapipe/calculators/core:constant_side_packet_calculator_cc_proto",
        "//mediapipe/calculators/core:side_packet_to_stream_calculator",
        "//mediapipe/calculators/tensor:audio_to_tensor_calculator",
        "//mediapipe/calculators/tensor:audio_to_tensor_calculator_cc_proto",
        "//mediapipe/calculators/tensor:inference_calculator_cpu",
        "//mediapipe/framework:calculator_cc_proto",
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/api2:builder",
        "//mediapipe/framework/api2:port",
        "//mediapipe/framework/formats:matrix",
        "//mediapipe/tasks/cc:common",
        "//mediapipe/tasks/cc/audio/audio_classifier/proto:audio_classifier_graph_options_cc_proto",
        "//mediapipe/tasks/cc/audio/utils:audio_tensor_specs",
        "//mediapipe/tasks/cc/components/containers/proto:classifications_cc_proto",
        "//mediapipe/tasks/cc/components/processors:classification_postprocessing_graph",
        "//mediapipe/tasks/cc/components/processors/proto:classification_postprocessing_graph_options_cc_proto",
        "//mediapipe/tasks/cc/core:model_resources",
        "//mediapipe/tasks/cc/core:model_task_graph",
        "//mediapipe/tasks/cc/core/proto:inference_subgraph_cc_proto",
        "//mediapipe/tasks/cc/metadata:metadata_extractor",
        "//mediapipe/tasks/metadata:metadata_schema_cc",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/status:statusor",
        "@com_google_absl//absl/types:optional",
        "@flatbuffers//:runtime_cc",
        "@org_tensorflow//tensorflow/lite/schema:schema_fbs",
    ],
    alwayslink = 1,
)

# TODO: mediapipe/tasks/cc/audio/utils:test_utils does not compile in the OSS build
