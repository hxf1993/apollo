load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "st_graph_point",
    srcs = [
        "st_graph_point.cc",
    ],
    hdrs = [
        "st_graph_point.h",
    ],
    deps = [
        "//modules/planning/common:planning_gflags",
        "//modules/planning/common/speed:st_point",
    ],
)

cc_library(
    name = "dp_st_cost",
    srcs = [
        "dp_st_cost.cc",
    ],
    hdrs = [
        "dp_st_cost.h",
    ],
    deps = [
        "//modules/common/proto:pnc_point_proto",
        "//modules/planning/common:frame",
        "//modules/planning/common/speed:st_boundary",
        "//modules/planning/math:double",
        "//modules/planning/proto:dp_st_speed_config_proto",
    ],
)

cc_library(
    name = "dp_st_graph",
    srcs = [
        "dp_st_graph.cc",
    ],
    hdrs = [
        "dp_st_graph.h",
    ],
    deps = [
        ":dp_st_cost",
        ":st_graph_point",
        "//modules/common/configs/proto:vehicle_config_proto",
        "//modules/common/proto:common_proto",
        "//modules/common/proto:pnc_point_proto",
        "//modules/common/status",
        "//modules/planning/common:path_decision",
        "//modules/planning/common/speed:speed_data",
        "//modules/planning/proto:planning_proto",
        "//modules/planning/tasks/st_graph:st_graph_data",
    ],
)

cc_library(
    name = "dp_st_speed_optimizer",
    srcs = [
        "dp_st_speed_optimizer.cc",
    ],
    hdrs = [
        "dp_st_speed_optimizer.h",
    ],
    deps = [
        ":dp_st_cost",
        ":dp_st_graph",
        "//modules/common/adapters:adapter_manager",
        "//modules/common/configs:vehicle_config_helper",
        "//modules/common/vehicle_state",
        "//modules/localization/proto:localization_proto",
        "//modules/planning/proto:dp_st_speed_config_proto",
        "//modules/planning/proto:planning_proto",
        "//modules/planning/tasks:speed_optimizer",
        "//modules/planning/tasks/st_graph:st_boundary_mapper",
        "//modules/planning/tasks/st_graph:st_graph_data",
    ],
)

cpplint()
