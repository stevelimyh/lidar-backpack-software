load("//engine/build:isaac.bzl", "isaac_app", "isaac_subgraph","isaac_cc_module")


isaac_app(
    name = "record_dummy",
    data = [
        "//packages/record_replay/apps:record_subgraph",
        "//new_app/record_dummy:imu_generator_subgraph",
    ],
    modules = [
        "message_generators",
    ]
)

isaac_app(
    name = "record_test",
    data = [
        "//packages/record_replay/apps:record_subgraph",
    ],
    modules = [
        "message_generators",
        "imu",
    ]
)

isaac_subgraph(
    name = "imu_generator_subgraph",
    modules = [
        "imu",
        "message_generators",
    ],
    subgraph = "imu_generator.subgraph.json",
    visibility = ["//visibility:public"],
)

isaac_app(
    name = "display_dummy",
    data = [
        "//packages/record_replay/apps:replay_subgraph",
    ],
    modules = [
        "viewers",
	"perception",
    ]
)

isaac_app(
    name = "display_test",
    data = [
        "//packages/record_replay/apps:replay_subgraph",
    ],
    modules = [
        "viewers",
        "perception",
        "imu",
    ]
)

isaac_app(
    name = "imu_test",
    app_json_file = "imu_test.app.json",
    data = [
        "//packages/record_replay/apps:record_subgraph",
        "imu_calib.json",
    ],
    modules = [
        "imu",
        "message_generators",
    ],
)
