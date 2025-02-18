# language-tasklist

Tasklist simple grammar. This package is provided for `TODO`, `*.todo`, and `*.tasklist` files.

![language-tasklist](https://github.com/asiloisad/pulsar-language-tasklist/blob/master/assets/example.png?raw=true)

## Installation

To install `language-tasklist` search for [language-tasklist](https://web.pulsar-edit.dev/packages/language-tasklist) in the Install pane of the Pulsar settings or run `ppm install language-tasklist`. Alternatively, you can run `ppm install asiloisad/pulsar-language-tasklist` to install a package directly from the Github repository.

## Tools

A superset of commands is provided by the [tasklist-tools](https://github.com/asiloisad/pulsar-tasklist-tools).

## Features

- A task is a single line consisting of a tick and text.
- Unicode characters have been used to represent ticks.
- There are several types of ticks:
  | Symbol | Code    | Name   | Description                    |
  |--------|---------|--------|--------------------------------|
  | `▷`    | `U+25B7`| `high` | a high priority pending task   |
  | `☐`    | `U+2610`| `todo` | a normal priority pending task |
  | `✔`    | `U+2714`| `done` | a done/pass/completed task     |
  | `✘`    | `U+2718`| `fail` | a failed/rejected task         |
  | `•`    | `U+2022`| `info` | a notes line                   |
- Any line starting with `#` is a chapter, indentation is not allowed, multilevel is supported.
- Any non-tick line ending with `:` is a header.
- Every line ending with `:` trigger an indentation.
- Support for `~text~`, `*text*`, `_text_`, `$text$` and ``text` `` formats.
- Tasklists can be included using the `tasklist` selector.
- Two space indentation is recommended.
- Outline & folding is provided by [navigation-panel](https://github.com/asiloisad/pulsar-navigation-panel).

## Customization

You can customize the tasklist by using custom CSS. Here are some examples:

- Add a line-through to `done` and `fail` tasks:

  ```less
  .syntax--tasklist {
    &.syntax--done, &.syntax--fail {
      &.syntax--text {
        text-decoration: line-through;
      }
    }
  }
  ```

- Set bold font-weight of chapters:

  ```less
  .syntax--tasklist {
    &.syntax--chapter {
      font-weight: bold;
    }
  }
  ```

- Change `high` tasks color:

  ```less
  .syntax--tasklist.syntax--high.syntax--text {
    color: red;
  }
  ```

# Contributing

Got ideas to make this package better, found a bug, or want to help add new features? Just drop your thoughts on GitHub — any feedback’s welcome!
