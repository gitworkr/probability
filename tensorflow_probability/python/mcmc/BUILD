# Copyright 2018 The TensorFlow Probability Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ============================================================================
# Description:
#   MCMC methods, diagnostics, and related utilities.

# [internal] load python3.bzl

package(
    default_visibility = [
        "//tensorflow_probability:__subpackages__",
    ],
)

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

py_library(
    name = "mcmc",
    srcs = ["__init__.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":diagnostic",
        ":hmc",
        ":kernel",
        ":langevin",
        ":metropolis_hastings",
        ":random_walk_metropolis",
        ":replica_exchange_mc",
        ":sample",
        ":sample_annealed_importance",
        ":sample_halton_sequence",
        ":slice_sampler_kernel",
        ":transformed_kernel",
    ],
)

py_library(
    name = "diagnostic",
    srcs = ["diagnostic.py"],
    srcs_version = "PY2AND3",
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability/python/stats",
    ],
)

py_test(
    name = "diagnostic_test",
    size = "medium",
    srcs = ["diagnostic_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "hmc",
    srcs = ["hmc.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":metropolis_hastings",
        ":util",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "hmc_test",
    size = "medium",
    srcs = ["hmc_test.py"],
    shard_count = 6,
    tags = [
        # TODO(b/80193238): Re-enable.
        "notap",
    ],
    deps = [
        # numpy dep,
        # scipy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "langevin",
    srcs = ["langevin.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":metropolis_hastings",
        ":util",
        "//tensorflow_probability/python/math:diag_jacobian",
    ],
)

py_test(
    name = "langevin_test",
    size = "medium",
    srcs = ["langevin_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "kernel",
    srcs = ["kernel.py"],
    srcs_version = "PY2AND3",
    deps = [
        # six dep,
    ],
)

py_library(
    name = "metropolis_hastings",
    srcs = ["metropolis_hastings.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":util",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_library(
    name = "replica_exchange_mc",
    srcs = ["replica_exchange_mc.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":util",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "metropolis_hastings_test",
    size = "small",
    srcs = ["metropolis_hastings_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "random_walk_metropolis",
    srcs = ["random_walk_metropolis.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":metropolis_hastings",
        ":util",
        # tensorflow dep,
    ],
)

py_test(
    name = "random_walk_metropolis_test",
    size = "medium",
    srcs = ["random_walk_metropolis_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "sample",
    srcs = ["sample.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":util",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "sample_test",
    size = "medium",
    srcs = ["sample_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "sample_annealed_importance",
    srcs = ["sample_annealed_importance.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":util",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "sample_annealed_importance_test",
    size = "medium",
    srcs = ["sample_annealed_importance_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "sample_halton_sequence",
    srcs = ["sample_halton_sequence.py"],
    srcs_version = "PY2AND3",
    deps = [
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "sample_halton_sequence_test",
    size = "medium",
    srcs = ["sample_halton_sequence_test.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
        "//tensorflow_probability/python/internal:monte_carlo",
    ],
)

py_library(
    name = "slice_sampler_kernel",
    srcs = ["slice_sampler_kernel.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel",
        ":slice_sampler_utils",
        ":util",
        # tensorflow dep,
    ],
)

py_library(
    name = "slice_sampler_utils",
    srcs = ["slice_sampler_utils.py"],
    srcs_version = "PY2AND3",
    deps = [
        # tensorflow dep,
    ],
)

py_test(
    name = "slice_sampler_test",
    size = "medium",
    timeout = "long",
    srcs = ["slice_sampler_test.py"],
    shard_count = 6,
    deps = [
        ":slice_sampler_utils",
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "transformed_kernel",
    srcs = ["transformed_kernel.py"],
    srcs_version = "PY2AND3",
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability/python/mcmc:kernel",
        "//tensorflow_probability/python/mcmc:util",
    ],
)

py_test(
    name = "transformed_kernel_test",
    size = "medium",
    srcs = ["transformed_kernel_test.py"],
    shard_count = 4,
    tags = ["tf2-broken"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "util",
    srcs = ["util.py"],
    srcs_version = "PY2AND3",
    deps = [
        # numpy dep,
        # tensorflow dep,
    ],
)

py_test(
    name = "util_test",
    size = "small",
    srcs = ["util_test.py"],
    deps = [
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "eight_schools_hmc",
    srcs = ["eight_schools_hmc.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

# bazel run -c opt :eight_schools_hmc_eager_test -- --benchmarks=.
py_test(
    name = "eight_schools_hmc_eager_test",
    size = "medium",  # Might run > 1 minute.
    srcs = ["eight_schools_hmc_eager_test.py"],
    deps = [
        ":eight_schools_hmc",
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

# bazel run -c opt :eight_schools_hmc_graph_test -- --benchmarks=.
py_test(
    name = "eight_schools_hmc_graph_test",
    size = "medium",  # Might run > 1 minute.
    srcs = ["eight_schools_hmc_graph_test.py"],
    deps = [
        ":eight_schools_hmc",
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

py_library(
    name = "text_messages_hmc",
    srcs = ["text_messages_hmc.py"],
    deps = [
        # numpy dep,
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

# bazel run -c opt :text_messages_hmc_eager_test -- --benchmarks=.
py_test(
    name = "text_messages_hmc_eager_test",
    size = "medium",  # Might run > 1 minute.
    srcs = ["text_messages_hmc_eager_test.py"],
    deps = [
        ":text_messages_hmc",
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)

# bazel run -c opt :text_messages_hmc_graph_test -- --benchmarks=.
py_test(
    name = "text_messages_hmc_graph_test",
    size = "medium",  # Might run > 1 minute.
    srcs = ["text_messages_hmc_graph_test.py"],
    deps = [
        ":text_messages_hmc",
        # tensorflow dep,
        "//tensorflow_probability",
    ],
)
