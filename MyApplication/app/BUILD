load("//tools/googleservices:defs.bzl", "google_services_xml")

GOOGLE_SERVICES_XML = google_services_xml(
    packageName = "com.example.myapplication",
    google_services_json = "google-services.json")

android_binary(
    name = "app",
    srcs = glob(["src/main/java/**/*.java"]),
    manifest = "src/main/AndroidManifest.xml",
    resource_files = glob(["src/main/res/**"]) + GOOGLE_SERVICES_XML,
    # this sets the java package for the R class, since this android_binary
    # rule isn't under a java root.
    custom_package = "com.example.myapplication",
    deps = [
        # these extra deps are necessary until the fix for
        # https://github.com/bazelbuild/bazel/issues/4472 is in a bazel release
        "@com_google_code_gson//jar","@com_google_firebase_firebase_messaging_11_8_0//aar",
        "@com_google_firebase_firebase_iid_11_8_0//aar",
        "@androidsdk//com.android.support:appcompat-v7-25.0.0",
        "@com_android_support_constraint_constraint_layout_1_0_2//aar",
        "@com_android_support_constraint_constraint_layout_solver_1_0_2//jar",
        "@com_android_support_support_core_utils_26_1_0//aar",
        "@com_android_support_support_v4_26_1_0//aar",
        "@com_android_support_support_core_ui_26_1_0//aar",
        "@com_google_firebase_firebase_common_11_8_0//aar:aar",
        "@com_android_support_support_fragment_26_1_0//aar",
        "@com_android_support_support_compat_26_1_0//aar",
        "@android_arch_lifecycle_runtime_1_0_0//aar",
        "@com_android_support_support_annotations_26_1_0//jar",
        "@android_arch_core_common_1_0_0//jar",
        "@android_arch_lifecycle_common_1_0_0//jar",
        "@com_google_android_gms_play_services_basement_11_8_0//aar",
        "@com_android_support_support_vector_drawable_26_1_0//aar",
        "@com_google_firebase_firebase_auth_11_8_0//aar",
        "@com_google_android_gms_play_services_base_11_8_0//aar:aar",
        "@com_google_android_gms_play_services_tasks_11_8_0//aar:aar",
    ],
    manifest_values = {
      "minSdkVersion": "15",
      "applicationId": "com.example.myapplication",
    }
)
