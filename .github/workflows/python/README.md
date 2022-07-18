The [python.yml](../python.yml) workflow is a simple workflow that can be used to against your python code to install dependencies and run black, flake8, pytest.

# Example Usage
```yaml
jobs:
  build:
    uses: AptivConnectedServices/public-workflows/.github/workflows/python.yml@main
    with:
      enable-pytest: false
```

More examples can be found in [examples](examples/)

# Inputs
TODO
