# repomark-action

GitHub Action wrapper for [@topdaily-dev/repomark](https://github.com/topdaily-dev/repomark).

## Usage

```yaml
name: Repo health

on:
  pull_request:
  push:
    branches: [main]

jobs:
  repomark:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: topdaily-dev/repomark-action@v1
        with:
          min: "70"
```

## Inputs

| Input | Default | Description |
|-------|---------|-------------|
| `directory` | `.` | Path to scan |
| `min` | `70` | Fail the step if score is below this value |
| `version` | `0.2.0` | npm version of `@topdaily-dev/repomark` to run |

## Bootstrap with collab-kit

Install the workflow file automatically:

```bash
npx @korykaai/collab-kit init . --oss-toolchain
```

This copies `.github/workflows/repomark.yml` and the rest of the OSS toolchain scaffold. See [collab-kit oss-toolchain](https://github.com/kory-kaai/collab-kit/blob/main/examples/oss-toolchain.md).

## License

MIT
