# Setup KubeDB Action
This action installs [clevyr/kubedb](https://github.com/clevyr/kubedb).

See the [kubedb](https://github.com/clevyr/kubedb#readme) readme for more details on running KubeDB.

## Usage

### Inputs
| Name      | Description                   | Required | Default                                             |
|-----------|-------------------------------|----------|-----------------------------------------------------|
| `version` | The KubeDB version to install | `false`  | `latest`                                            |
| `repo`    | The KubeDB repo to use        | `false`  | [`clevyr/kubedb`](https://github.com/clevyr/kubedb) |
| `token`   | GitHub Token                  | `false`  | `${{ github.token }}`                               |

### Outputs

| Name      | Description                           |
|-----------|---------------------------------------|
| `version` | The KubeDB version that was installed |

## Example Workflow
Here is an example that fetches a separate deployment repo and patches its configuration.

```yaml
name: Patch Configuration

on: push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: clevyr/setup-kubedb-action@v1
      - run: kubedb dump ...
```
