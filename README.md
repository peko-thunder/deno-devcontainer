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

### start dev container

Open this project in VSCode to create a container.

### git clone

For developer, clone forked repository path.

```bash
$ cd /workspace/
$ git clone --recurse-submodules https://github.com/denoland/deno.git ./deno
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

Can set "deno" path.

```bash
$ vim ~/.bashrc
# Insert 
> export PATH="/workspace/deno/target/debug:$PATH"
$ source ~/.bashrc
$ deno --version
```

## Extension

If the `denoland.vscode-deno` extension is disabled, please enable it.

## Use ssh in container

ssh-agent allows local credentials to be used in containers.

> https://code.visualstudio.com/remote/advancedcontainers/sharing-git-credentials

If ssn-agent is able to transfer to the container, but the key is not available via SSH.
If you have a low version of OpenSSH on Windows, the specification cannot be used for security purposes.

```bash
$ ssh -V
> OpenSSH_for_Windows_9.5p1, LibreSSL 3.8.2
```

> https://zenn.dev/took/articles/a9c258967f336c
