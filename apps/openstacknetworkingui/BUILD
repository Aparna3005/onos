EXCLUDE_PACKAGES = "!org.apache.sshd.client,!org.apache.sshd.client.*,!org.apache.sshd.common.util.io"

COMPILE_DEPS = CORE_DEPS + JACKSON + CLI + REST + [
    "//core/store/serializers:onos-core-serializers",
    "//apps/openstacknode/api:onos-apps-openstacknode-api",
    "//apps/openstacknetworking/api:onos-apps-openstacknetworking-api",
    "@sshd_core//jar",
]

EXCLUDED_BUNDLES = [
    "@sshd_core//jar",
]

TEST_DEPS = TEST_ADAPTERS + [
    "//core/api:onos-api-tests",
    "//core/common:onos-core-common-tests",
]

osgi_jar_with_tests(
    import_packages = EXCLUDE_PACKAGES,
    test_deps = TEST_DEPS,
    deps = COMPILE_DEPS,
)

onos_app(
    app_name = "org.onosproject.openstacknetworkingui",
    category = "GUI",
    description = "Openstack Networking UI Service",
    excluded_bundles = EXCLUDED_BUNDLES,
    required_apps = [
        "org.onosproject.openstacknetworking",
    ],
    title = "Openstack Networking UI",
    url = "http://onosproject.org",
)