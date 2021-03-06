package_group(
    name = "default_visibility",
    includes = ["//tensorflow_federated/python/core/impl:core_visibility"],
    packages = [
        # Subpackages
        "//tensorflow_federated/python/core/impl/context_stack/...",

        # Impl Dependencies
        "//tensorflow_federated/python/core/impl/wrappers/...",

        # TODO(b/143772942): This package is temporary and can be removed once
        # all the appropriate modules have been moved out of the `impl` package.
        "//tensorflow_federated/python/core/impl",
    ],
)

package(default_visibility = [":default_visibility"])

licenses(["notice"])

py_library(
    name = "context_stack",
    srcs = ["__init__.py"],
    srcs_version = "PY3",
    visibility = ["//tensorflow_federated/tools:__subpackages__"],
)

py_library(
    name = "context_stack_impl",
    srcs = ["context_stack_impl.py"],
    srcs_version = "PY3",
    deps = [
        "//tensorflow_federated/python/common_libs:py_typecheck",
        "//tensorflow_federated/python/core/impl:context_base",
        "//tensorflow_federated/python/core/impl:context_stack_base",
        "//tensorflow_federated/python/core/impl/executors:execution_context",
        "//tensorflow_federated/python/core/impl/executors:executor_stacks",
    ],
)

py_test(
    name = "context_stack_impl_test",
    size = "small",
    srcs = ["context_stack_impl_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":context_stack_impl",
        ":context_stack_test_utils",
    ],
)

py_library(
    name = "context_stack_test_utils",
    srcs = ["context_stack_test_utils.py"],
    srcs_version = "PY3",
    deps = ["//tensorflow_federated/python/core/impl:context_base"],
)

py_library(
    name = "get_context_stack",
    srcs = ["get_context_stack.py"],
    srcs_version = "PY3",
    deps = [":context_stack_impl"],
)

py_test(
    name = "get_context_stack_test",
    size = "small",
    srcs = ["get_context_stack_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":context_stack_impl",
        ":get_context_stack",
    ],
)

py_library(
    name = "set_default_context",
    srcs = ["set_default_context.py"],
    srcs_version = "PY3",
    deps = [":context_stack_impl"],
)

py_test(
    name = "set_default_context_test",
    size = "small",
    srcs = ["set_default_context_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":context_stack_impl",
        ":context_stack_test_utils",
        ":set_default_context",
    ],
)

py_library(
    name = "set_default_executor",
    srcs = ["set_default_executor.py"],
    srcs_version = "PY3",
    deps = [
        ":context_stack_impl",
        "//tensorflow_federated/python/core/impl:reference_executor",
        "//tensorflow_federated/python/core/impl/executors:execution_context",
        "//tensorflow_federated/python/core/impl/executors:executor_factory",
    ],
)

py_test(
    name = "set_default_executor_test",
    size = "small",
    srcs = ["set_default_executor_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":context_stack_impl",
        ":context_stack_test_utils",
        ":set_default_executor",
        "//tensorflow_federated/python/core/impl:reference_executor",
        "//tensorflow_federated/python/core/impl/executors:execution_context",
        "//tensorflow_federated/python/core/impl/executors:executor_factory",
    ],
)
