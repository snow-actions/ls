# ls

[![Test](https://github.com/snow-actions/ls/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/snow-actions/ls/actions/workflows/test.yml)

`ls` to JSON.

## Usage

```yml
steps:
  - id: ls
    uses: snow-actions/ls@v1.0.0
  - run: echo "${json}"
    env:
      json: ${{ steps.ls.outputs.json }}
```

## Inputs & Outputs

See [action.yml](action.yml)

### Inputs

| Name | Description | Default | Required |
| - | - | - | - |
| `path` | Path | `.` | yes |
| `dotfiles` | Include dotfiles | `false` | no |

### Outputs

| Name | Description |
| - | - |
| `json` | JSON |

## Supported

### Runners

- `ubuntu-*`
- `windows-*`
- `macos-*`
- `self-hosted`

### Events

- Any

## Dependencies

- Bash
- [jq](https://stedolan.github.io/jq/)

## Contributing

Welcome.
