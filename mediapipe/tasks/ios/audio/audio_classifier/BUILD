# Copyright 2024 The MediaPipe Authors.
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

package(default_visibility = ["//visibility:public"])

licenses(["notice"])

objc_library(
    name = "MPPAudioClassifierResult",
    srcs = ["sources/MPPAudioClassifierResult.m"],
    hdrs = ["sources/MPPAudioClassifierResult.h"],
    deps = [
        "//mediapipe/tasks/ios/components/containers:MPPClassificationResult",
        "//mediapipe/tasks/ios/core:MPPTaskResult",
        "//third_party/apple_frameworks:Foundation",
    ],
)

objc_library(
    name = "MPPAudioClassifierOptions",
    srcs = ["sources/MPPAudioClassifierOptions.m"],
    hdrs = ["sources/MPPAudioClassifierOptions.h"],
    deps = [
        ":MPPAudioClassifierResult",
        "//mediapipe/tasks/ios/audio/core:MPPAudioRunningMode",
        "//mediapipe/tasks/ios/core:MPPTaskOptions",
        "//third_party/apple_frameworks:Foundation",
    ],
)

objc_library(
    name = "MPPAudioClassifier",
    srcs = ["sources/MPPAudioClassifier.mm"],
    hdrs = ["sources/MPPAudioClassifier.h"],
    copts = [
        "-ObjC++",
        "-std=c++20",
        "-Xclang=-fno-cxx-modules",
        "-x objective-c++",
    ],
    deps = [
        ":MPPAudioClassifierOptions",
        ":MPPAudioClassifierResult",
        "//mediapipe/tasks/cc/audio/audio_classifier:audio_classifier_graph",
        "//mediapipe/tasks/ios/audio/audio_classifier/utils:MPPAudioClassifierOptionsHelpers",
        "//mediapipe/tasks/ios/audio/audio_classifier/utils:MPPAudioClassifierResultHelpers",
        "//mediapipe/tasks/ios/audio/core:MPPAudioData",
        "//mediapipe/tasks/ios/audio/core:MPPAudioRecord",
        "//mediapipe/tasks/ios/audio/core:MPPAudioTaskRunner",
        "//mediapipe/tasks/ios/common/utils:MPPCommonUtils",
        "//mediapipe/tasks/ios/common/utils:NSStringHelpers",
        "//mediapipe/tasks/ios/core:MPPTaskInfo",
        "//third_party/apple_frameworks:Foundation",
    ],
)
