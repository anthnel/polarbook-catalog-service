# Build
custom_build(
    # Name of the container image
    ref = 'registry.home.lan:80/catalog-service',
    # Command to build the container image
    command = 'gradle bootBuildImage --imageName $EXPECTED_REF',
    command_bat = 'gradle bootBuildImage --imageName %EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(kustomize('k8s'))

# Manage
k8s_resource('catalog-service', port_forwards=['9001'])