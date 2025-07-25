# Copyright 2023 The MediaPipe Authors.
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

load("//mediapipe/framework:encode_binary_proto.bzl", "encode_binary_proto")

licenses(["notice"])

package(
    default_visibility = ["//visibility:public"],
)

encode_binary_proto(
    name = "geometry_pipeline_metadata_detection",
    input = "geometry_pipeline_metadata_detection.pbtxt",
    message_type = "mediapipe.tasks.vision.face_geometry.proto.GeometryPipelineMetadata",
    output = "geometry_pipeline_metadata_detection.binarypb",
    deps = [
        "//mediapipe/tasks/cc/vision/face_geometry/proto:geometry_pipeline_metadata_proto",
    ],
)

encode_binary_proto(
    name = "geometry_pipeline_metadata_landmarks",
    input = "geometry_pipeline_metadata_landmarks.pbtxt",
    message_type = "mediapipe.tasks.vision.face_geometry.proto.GeometryPipelineMetadata",
    output = "geometry_pipeline_metadata_landmarks.binarypb",
    deps = [
        "//mediapipe/tasks/cc/vision/face_geometry/proto:geometry_pipeline_metadata_proto",
    ],
)

# For backward-compatibility reasons, generate `geometry_pipeline_metadata.binarypb` from
# the `geometry_pipeline_metadata_landmarks.pbtxt` definition.
encode_binary_proto(
    name = "geometry_pipeline_metadata",
    input = "geometry_pipeline_metadata_landmarks.pbtxt",
    message_type = "mediapipe.tasks.vision.face_geometry.proto.GeometryPipelineMetadata",
    output = "geometry_pipeline_metadata.binarypb",
    deps = [
        "//mediapipe/tasks/cc/vision/face_geometry/proto:geometry_pipeline_metadata_proto",
    ],
)

# These canonical face model files are not meant to be used in runtime, but rather for asset
# creation and/or reference.
exports_files([
    "canonical_face_model.fbx",
    "canonical_face_model.obj",
    "canonical_face_model_uv_visualization.png",
])
