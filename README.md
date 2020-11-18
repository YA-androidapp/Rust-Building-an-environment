# Rust-Building-an-environment

Rust 開発環境構築

---

## Rust ツールチェーンのインストール

https://rustup.rs に記載されているコマンドを実行する

### Unix

```sh
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
info: downloading installer

Welcome to Rust!

This will download and install the official compiler for the Rust
programming language, and its package manager, Cargo.

Rustup metadata and toolchains will be installed into the Rustup
home directory, located at:

  /Users/yu/.rustup

This can be modified with the RUSTUP_HOME environment variable.

The Cargo home directory located at:

  /Users/yu/.cargo

This can be modified with the CARGO_HOME environment variable.

The cargo, rustc, rustup and other commands will be added to
Cargo's bin directory, located at:

  /Users/yu/.cargo/bin

This path will then be added to your PATH environment variable by
modifying the profile files located at:

  /Users/yu/.profile
  /Users/yu/.zprofile

You can uninstall at any time with rustup self uninstall and
these changes will be reverted.

Current installation options:


   default host triple: x86_64-apple-darwin
     default toolchain: stable (default)
               profile: default
  modify PATH variable: yes

1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
>1

info: profile set to 'default'
info: default host triple is x86_64-apple-darwin
info: syncing channel updates for 'stable-x86_64-apple-darwin'
info: latest update on 2020-10-08, rust version 1.47.0 (18bf6b4f0 2020-10-07)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
info: downloading component 'rust-std'
 19.7 MiB /  19.7 MiB (100 %)  18.9 MiB/s in  1s ETA:  0s
info: downloading component 'rustc'
 50.6 MiB /  50.6 MiB (100 %)  18.6 MiB/s in  2s ETA:  0s
info: downloading component 'rustfmt'
info: installing component 'cargo'
info: Defaulting to 500.0 MiB unpack ram
info: installing component 'clippy'
info: installing component 'rust-docs'
 12.9 MiB /  12.9 MiB (100 %)   8.1 MiB/s in  1s ETA:  0s
info: installing component 'rust-std'
 19.7 MiB /  19.7 MiB (100 %)  12.2 MiB/s in  1s ETA:  0s
info: installing component 'rustc'
 50.6 MiB /  50.6 MiB (100 %)  13.6 MiB/s in  3s ETA:  0s
info: installing component 'rustfmt'
info: default toolchain set to 'stable'

  stable installed - rustc 1.47.0 (18bf6b4f0 2020-10-07)


Rust is installed now. Great!

To get started you need Cargo's bin directory ($HOME/.cargo/bin) in your PATH
environment variable. Next time you log in this will be done
automatically.

To configure your current shell run source $HOME/.cargo/env
$ source $HOME/.cargo/env
```

### Windows

[Windows 64-bit, rustup-init.exe](https://win.rustup.rs/x86_64)

### プロジェクト作成

```sh
$ cargo new hello
     Created binary (application) `hello` package
$ tree hello
hello
├── Cargo.toml
└── src
    └── main.rs

1 directory, 2 files
```

### コンパイルと実行

```sh
$ cd hello
$ cargo run
   Compiling hello v0.1.0 (/Users/yu/Documents/GitHub/Rust-Building-an-environment/hello)
    Finished dev [unoptimized + debuginfo] target(s) in 3.79s
     Running `target/debug/hello`
Hello, world!
```
