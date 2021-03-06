package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "cache_comparer.go",
        "factory.go",
        "plugins.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:darwin": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:dragonfly": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:freebsd": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:nacl": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:netbsd": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:openbsd": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:plan9": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:solaris": [
            "signal.go",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "signal_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "k8s.io/kubernetes/pkg/scheduler/factory",
    deps = [
        "//pkg/api/v1/pod:go_default_library",
        "//pkg/apis/core/helper:go_default_library",
        "//pkg/features:go_default_library",
        "//pkg/kubelet/apis:go_default_library",
        "//pkg/scheduler:go_default_library",
        "//pkg/scheduler/algorithm:go_default_library",
        "//pkg/scheduler/algorithm/predicates:go_default_library",
        "//pkg/scheduler/algorithm/priorities:go_default_library",
        "//pkg/scheduler/api:go_default_library",
        "//pkg/scheduler/api/validation:go_default_library",
        "//pkg/scheduler/cache:go_default_library",
        "//pkg/scheduler/core:go_default_library",
        "//pkg/scheduler/util:go_default_library",
        "//pkg/scheduler/volumebinder:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/api/policy/v1beta1:go_default_library",
        "//vendor/k8s.io/api/storage/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/errors:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/fields:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/labels:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/types:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//vendor/k8s.io/apiserver/pkg/util/feature:go_default_library",
        "//vendor/k8s.io/client-go/informers/apps/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/informers/core/v1:go_default_library",
        "//vendor/k8s.io/client-go/informers/extensions/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/informers/policy/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/informers/storage/v1:go_default_library",
        "//vendor/k8s.io/client-go/kubernetes:go_default_library",
        "//vendor/k8s.io/client-go/listers/apps/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/listers/core/v1:go_default_library",
        "//vendor/k8s.io/client-go/listers/extensions/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/listers/policy/v1beta1:go_default_library",
        "//vendor/k8s.io/client-go/listers/storage/v1:go_default_library",
        "//vendor/k8s.io/client-go/tools/cache:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "cache_comparer_test.go",
        "factory_test.go",
        "plugins_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//pkg/api/testing:go_default_library",
        "//pkg/scheduler:go_default_library",
        "//pkg/scheduler/algorithm:go_default_library",
        "//pkg/scheduler/algorithm/priorities:go_default_library",
        "//pkg/scheduler/api:go_default_library",
        "//pkg/scheduler/api/latest:go_default_library",
        "//pkg/scheduler/cache:go_default_library",
        "//pkg/scheduler/core:go_default_library",
        "//pkg/scheduler/testing:go_default_library",
        "//pkg/scheduler/util:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/api/policy/v1beta1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/resource:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/types:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//vendor/k8s.io/client-go/informers:go_default_library",
        "//vendor/k8s.io/client-go/kubernetes:go_default_library",
        "//vendor/k8s.io/client-go/rest:go_default_library",
        "//vendor/k8s.io/client-go/tools/cache:go_default_library",
        "//vendor/k8s.io/client-go/util/testing:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
