The [docker.yml](../docker.yml) workflow is a simple workflow that can be used to build Docker images and optionally push them to the ghcr.io registry.

# Example Usage
```
jobs:
  example:
    uses: AptivConnectedServices/public-workflows/.github/workflows/docker.yml@main
    with:
      image-name: ${{ github.repository }}
      push: false
```

More examples can be found in [examples](examples/)

# Inputs
- `image-name` (string): The name of the image to build. This name is prepended with `ghcr.io`. For example if the `image-name` = `my-image`, the full image will be named `ghcr.io/my-image`.
- `push` (boolean): Whether to push the image to the ghcr.io registry. Defaults to `false`.
