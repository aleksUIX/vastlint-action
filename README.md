# vastlint-action

Created by [Aleksander Sekowski](https://github.com/aleksUIX).

GitHub Action to validate VAST XML in CI using the `vastlint` CLI.

## Usage

```yaml
name: Validate VAST

on:
  pull_request:
  push:
    branches: [main]

jobs:
  vastlint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Validate VAST tags
        uses: aleksUIX/vastlint-action@v1
        with:
          path: tags/**/*.xml
          fail-on-warning: "true"
```

## Inputs

- `path` (default: `tags/**/*.xml`): File, glob, or directory to validate.
- `version` (default: `latest`): `vastlint` release tag (for example `v0.11.1`) or `latest`.
- `fail-on-warning` (default: `false`): Set to `true` to fail on warnings.
- `format` (default: empty): Optional output format, for example `json`.
- `extra-args` (default: empty): Extra arguments appended to `vastlint check`.

## Notes

- Supported runners: Linux and macOS.
- This action downloads release binaries from `aleksUIX/vastlint`.

## License

Apache-2.0
