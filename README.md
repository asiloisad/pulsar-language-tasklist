# language-tasklist

Syntax highlighting for tasklist files. Provides grammar for `TODO`, `*.todo`, and `*.tasklist` files with Unicode tick symbols.

![language-tasklist](https://github.com/asiloisad/pulsar-language-tasklist/blob/master/assets/example.png?raw=true)

## Features

- **Unicode ticks**: Multiple task states using Unicode symbols.
- **Chapters & headers**: Support for `#` chapters and `:` headers.
- **Text formatting**: Support for `~text~`, `*text*`, `_text_`, `$text$` and `` `text` ``.
- **Outline support**: Folding via [navigation-panel](https://github.com/asiloisad/pulsar-navigation-panel).
- **[tasklist-tools](https://github.com/asiloisad/pulsar-tasklist-tools)**: Commands for task toggling and navigation.

## Installation

To install `language-tasklist` search for [language-tasklist](https://web.pulsar-edit.dev/packages/language-tasklist) in the Install pane of the Pulsar settings or run `ppm install language-tasklist`. Alternatively, you can run `ppm install asiloisad/pulsar-language-tasklist` to install a package directly from the GitHub repository.

## Syntax

A task is a single line consisting of a tick and text. Unicode characters represent ticks:

| Symbol | Code | Name | Description |
| --- | --- | --- | --- |
| `▷` | `U+25B7` | `high` | high priority pending task |
| `☐` | `U+2610` | `todo` | normal priority pending task |
| `✔` | `U+2714` | `done` | done/completed task |
| `✘` | `U+2718` | `fail` | failed/rejected task |
| `•` | `U+2022` | `info` | notes line |

- Lines starting with `#` are chapters (multilevel supported).
- Non-tick lines ending with `:` are headers.
- Two space indentation is recommended.

## Customization

The style can be adjusted according to user preferences in the `styles.less` file:

- e.g. add line-through to done and fail tasks:

  ```less
  .syntax--tasklist {
    &.syntax--done, &.syntax--fail {
      &.syntax--text {
        text-decoration: line-through;
      }
    }
  }
  ```

- e.g. set bold font-weight of chapters:

  ```less
  .syntax--tasklist {
    &.syntax--chapter {
      font-weight: bold;
    }
  }
  ```

- e.g. change high tasks color:

  ```less
  .syntax--tasklist.syntax--high.syntax--text {
    color: red;
  }
  ```

## Contributing

Got ideas to make this package better, found a bug, or want to help add new features? Just drop your thoughts on GitHub — any feedback's welcome!
