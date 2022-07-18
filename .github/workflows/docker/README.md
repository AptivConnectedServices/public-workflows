The [docker.yml](../docker.yml) workflow is a simple workflow that can be used to build Docker images and optionally push them to the ghcr.io registry.

# Example Usage
```yaml
jobs:
  example:
    uses: AptivConnectedServices/public-workflows/.github/workflows/docker.yml@main
    with:
      name: ${{ github.repository }}
      push: ${{ github.event_name == 'push' }}
```

More examples can be found in [examples](examples/)

# Inputs
- `name` (string): The name of the image to build. This name is prepended with `ghcr.io`. For example if the `name` = `my-image`, the full image will be named `ghcr.io/my-image`.
- `push` (boolean): Whether to push the image to the ghcr.io registry. Defaults to `false`.
- `context` (string): The path to the directory to use as the context for the build. Defaults to the current directory.
- `dockerfile` (string): The path to the Dockerfile to use for the build. Defaults to `Dockerfile`.
