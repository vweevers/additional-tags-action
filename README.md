# additional-tags-action

**A [GitHub Action](https://github.com/features/actions) to create major and minor git tags from the last tag.**

![GitHub tag](https://img.shields.io/github/v/tag/vweevers/additional-tags-action?sort=semver)
[![License](https://img.shields.io/github/license/vweevers/additional-tags-action)](LICENSE)

## Usage

```yaml
on:
  push:
    tags:
      - v[0-9]+.[0-9]+.[0-9]+
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: vweevers/additional-tags-action@v2
```

If your tag is `v2.4.8` (for example) then this action will create 2 additional tags (`v2` and `v2.4`) and push them to GitHub, replacing existing tags. If the tag is a prerelease (not x.x.x) or not prefixed with `v` then nothing happens.

## Why

Useful to release actions. Consumers of your action can now pin to either a:

- Major version (`uses: my-action@v2`)
- Minor version (`uses: my-action@v2.4`)
- Exact version (`uses: my-action@v2.4.8`)

## Inputs

None.

## License

[MIT](LICENSE)
