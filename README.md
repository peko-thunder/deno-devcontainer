# deno-devcontainer

Create a development container for "deno".

Multiple tools need to be installed on the local machine, with different setup methods for Windows and Mac.

> Deno Build Manual
> https://docs.deno.com/runtime/manual/references/contributing/building_from_source

## Caution

- This repository is created by a Windows user.
- Not verified on Mac.
- Deno version upgrade may make this repository unusable.

## Require

Use the VSCode extensions to edit files in the container.

- VSCode & Extensions
  - Dev Containers: v0.362.0
- Docker: v20.10.22

## Setup

### Dockerfile

Set forked repository path.

```
ARG REPO="https://github.com/xxx/deno.git"
```

## Build

```bash
$ cd /workspace/deno
$ cargo build -vv
```

## Run

The "deno" command can be used.

```bash
$ cd /workspace/deno
$ ./target/debug/deno --version
$ ./target/debug/deno run tests/testdata/run/002_hello.ts
```

## [WIP]Remarks

以下メモ

検証中の内容を含む

ローカルマシーンでgitに有効な認証を持っていれば、VSCodeからコミットすることが可能です。

> Commit from VSCode as long as you have a valid authentication to git on your local machine.

bind-mountだとdenoをビルドできないが、named-mountだとビルド可能である

> With bind-mount, deno cannot be built, but with named-mount, it can be built.
