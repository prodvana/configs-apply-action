# configs-apply Github Action

This action is used to automatically apply Prodvana config files in a repository.


# Requirements
- [pvnctl](https://github.com/prodvana/pvnctl) present in the CI environment
  - We recommend using [init-pvnctl-action](https://github.com/prodvana/init-pvnctl-action) to handle installation and authentication initialization

# Usage

## Inputs

| Input         | Default    | Description                                                                                                                                              |
| ------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| path          | (required) | Path to configs to apply. Can include ... to apply all subdirectories.                                                                                   |
| auth_context  | default    | pvnctl auth context to use. If you're using this action with init-pvnctl, leave as the default                                                           |


## Basic Usage

```yaml
steps:
  # pvnctl must be installed in your Action environment for configs-apply
  - uses: prodvana/init-pvnctl-action@v0.1.0 
    with:
      org: my-org
      api_token: ${{ secrets.YOUR_PRODVANA_API_TOKEN }}
  - uses: prodvana/configs-apply-action@v0.1.0
    with:
      path: pvn-configs/...
  - uses: prodvana/configs-apply-action@v0.1.0
    with:
      path: path/to/a/config.pvn.yaml
```
