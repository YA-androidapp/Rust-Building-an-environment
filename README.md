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

## VS Code のセットアップ

### Language Server

```sh
$ rustup component add rls rust-analysis rust-src
info: downloading component 'rls'
info: installing component 'rls'
info: Defaulting to 500.0 MiB unpack ram
info: downloading component 'rust-analysis'
info: installing component 'rust-analysis'
info: downloading component 'rust-src'
info: installing component 'rust-src'
$ cargo install cargo-edit
    Updating crates.io index
  Downloaded cargo-edit v0.7.0
  Downloaded 1 crate (57.6 KB) in 1.72s
  Installing cargo-edit v0.7.0
  Downloaded fnv v1.0.7
  Downloaded httpdate v0.3.2
  Downloaded iovec v0.1.4
  Downloaded pin-utils v0.1.0
  Downloaded env_proxy v0.4.1
  Downloaded either v1.6.1
  Downloaded futures-task v0.3.8
  Downloaded http v0.2.1
  Downloaded thread_local v1.0.1
  Downloaded serde v1.0.117
  Downloaded proc-macro2 v1.0.24
  Downloaded base64 v0.12.3
  Downloaded unicode-normalization v0.1.15
  Downloaded autocfg v1.0.1
  Downloaded form_urlencoded v1.0.0
  Downloaded dirs-sys v0.3.5
  Downloaded adler v0.2.3
  Downloaded cfg-if v0.1.10
  Downloaded aho-corasick v0.7.15
  Downloaded failure_derive v0.1.8
  Downloaded dtoa v0.4.6
  Downloaded cc v1.0.62
  Downloaded lazy_static v1.4.0
  Downloaded httparse v1.3.4
  Downloaded ipnet v2.3.0
  Downloaded indexmap v1.6.0
  Downloaded hashbrown v0.9.1
  Downloaded http-body v0.3.1
  Downloaded futures-channel v0.3.8
  Downloaded bitflags v1.2.1
  Downloaded log v0.4.11
  Downloaded miniz_oxide v0.4.3
  Downloaded ansi_term v0.11.0
  Downloaded atty v0.2.14
  Downloaded addr2line v0.14.0
  Downloaded mime v0.3.16
  Downloaded mime_guess v2.0.3
  Downloaded bytes v0.5.6
  Downloaded num-integer v0.1.44
  Downloaded proc-macro-error-attr v1.0.4
  Downloaded futures-io v0.3.8
  Downloaded futures-sink v0.3.8
  Downloaded core-foundation-sys v0.8.2
  Downloaded core-foundation v0.9.1
  Downloaded rand_core v0.5.1
  Downloaded semver-parser v0.7.0
  Downloaded strsim v0.8.0
  Downloaded semver v0.10.0
  Downloaded heck v0.3.1
  Downloaded tokio-tls v0.3.1
  Downloaded hex v0.4.2
  Downloaded pin-project v0.4.27
  Downloaded num_cpus v1.13.0
  Downloaded tinyvec_macros v0.1.0
  Downloaded once_cell v1.5.2
  Downloaded structopt v0.3.20
  Downloaded semver v0.11.0
  Downloaded semver-parser v0.10.1
  Downloaded subprocess v0.2.6
  Downloaded security-framework v2.0.0
  Downloaded textwrap v0.11.0
  Downloaded synstructure v0.12.4
  Downloaded time v0.1.44
  Downloaded security-framework-sys v2.0.0
  Downloaded percent-encoding v2.1.0
  Downloaded quote v1.0.7
  Downloaded pin-project-internal v0.4.27
  Downloaded serde_derive v1.0.117
  Downloaded tinyvec v1.0.1
  Downloaded pkg-config v0.3.19
  Downloaded matches v0.1.8
  Downloaded failure v0.1.8
  Downloaded rustc-demangle v0.1.18
  Downloaded remove_dir_all v0.5.3
  Downloaded pin-project v1.0.1
  Downloaded termcolor v1.1.0
  Downloaded openssl-sys v0.9.58
  Downloaded linked-hash-map v0.5.3
  Downloaded tempfile v3.1.0
  Downloaded structopt-derive v0.4.13
  Downloaded unicode-xid v0.2.1
  Downloaded want v0.3.0
  Downloaded unicase v2.6.0
  Downloaded toml v0.5.7
  Downloaded tokio-util v0.3.1
  Downloaded ucd-trie v0.1.3
  Downloaded void v1.0.2
  Downloaded version_check v0.9.2
  Downloaded vec_map v0.8.2
  Downloaded url v2.2.0
  Downloaded unreachable v1.0.0
  Downloaded mio v0.6.22
  Downloaded pest v2.1.3
  Downloaded reqwest v0.10.8
  Downloaded unicode-width v0.1.8
  Downloaded toml_edit v0.2.0
  Downloaded serde_urlencoded v0.6.1
  Downloaded cfg-if v1.0.0
  Downloaded serde_json v1.0.59
  Downloaded unicode-bidi v0.3.4
  Downloaded unicode-segmentation v1.7.0
  Downloaded tracing v0.1.21
  Downloaded rand v0.7.3
  Downloaded futures-util v0.3.8
  Downloaded hyper v0.13.9
  Downloaded combine v3.8.1
  Downloaded h2 v0.2.7
  Downloaded object v0.22.0
  Downloaded git2 v0.13.12
  Downloaded try-lock v0.2.3
  Downloaded regex v1.4.2
  Downloaded tracing-futures v0.2.4
  Downloaded tower-service v0.3.0
  Downloaded clap v2.33.3
  Downloaded syn v1.0.48
  Downloaded backtrace v0.3.54
  Downloaded socket2 v0.3.16
  Downloaded tracing-core v0.1.17
  Downloaded libz-sys v1.1.2
  Downloaded getrandom v0.1.15
  Downloaded regex-syntax v0.6.21
  Downloaded rand_chacha v0.2.2
  Downloaded proc-macro-error v1.0.4
  Downloaded idna v0.2.0
  Downloaded tokio v0.2.23
  Downloaded gimli v0.23.0
  Downloaded encoding_rs v0.8.26
  Downloaded libgit2-sys v0.12.14+1.1.0
  Downloaded error-chain v0.12.4
  Downloaded ryu v1.0.5
  Downloaded ascii v0.9.3
  Downloaded libc v0.2.80
  Downloaded ppv-lite86 v0.2.10
  Downloaded libssh2-sys v0.2.19
  Downloaded num-traits v0.2.14
  Downloaded itoa v0.4.6
  Downloaded slab v0.4.2
  Downloaded pin-project-lite v0.1.11
  Downloaded pin-project-internal v1.0.1
  Downloaded native-tls v0.2.6
  Downloaded net2 v0.2.35
  Downloaded dirs v3.0.1
  Downloaded chrono v0.4.19
  Downloaded cargo_metadata v0.11.4
  Downloaded memchr v2.3.4
  Downloaded byteorder v1.3.4
  Downloaded jobserver v0.1.21
  Downloaded hyper-tls v0.4.3
  Downloaded futures-core v0.3.8
  Downloaded 149 crates (12.6 MB) in 3.43s (largest was `libgit2-sys` at 1.6 MB)
   Compiling libc v0.2.80
   Compiling proc-macro2 v1.0.24
   Compiling autocfg v1.0.1
   Compiling unicode-xid v0.2.1
   Compiling syn v1.0.48
   Compiling cfg-if v0.1.10
   Compiling version_check v0.9.2
   Compiling log v0.4.11
   Compiling lazy_static v1.4.0
   Compiling memchr v2.3.4
   Compiling pkg-config v0.3.19
   Compiling bitflags v1.2.1
   Compiling getrandom v0.1.15
   Compiling serde_derive v1.0.117
   Compiling bytes v0.5.6
   Compiling itoa v0.4.6
   Compiling futures-core v0.3.8
   Compiling serde v1.0.117
   Compiling fnv v1.0.7
   Compiling slab v0.4.2
   Compiling pin-project-lite v0.1.11
   Compiling core-foundation-sys v0.8.2
   Compiling pin-project-internal v0.4.27
   Compiling matches v0.1.8
   Compiling tinyvec_macros v0.1.0
   Compiling ppv-lite86 v0.2.10
   Compiling once_cell v1.5.2
   Compiling percent-encoding v2.1.0
   Compiling cfg-if v1.0.0
   Compiling native-tls v0.2.6
   Compiling httparse v1.3.4
   Compiling pin-utils v0.1.0
   Compiling futures-io v0.3.8
   Compiling remove_dir_all v0.5.3
   Compiling hashbrown v0.9.1
   Compiling futures-sink v0.3.8
   Compiling ryu v1.0.5
   Compiling try-lock v0.2.3
   Compiling byteorder v1.3.4
   Compiling gimli v0.23.0
   Compiling adler v0.2.3
   Compiling ucd-trie v0.1.3
   Compiling unicode-segmentation v1.7.0
   Compiling tower-service v0.3.0
   Compiling failure_derive v0.1.8
   Compiling encoding_rs v0.8.26
   Compiling rustc-demangle v0.1.18
   Compiling void v1.0.2
   Compiling httpdate v0.3.2
   Compiling object v0.22.0
   Compiling serde_json v1.0.59
   Compiling unicode-width v0.1.8
   Compiling either v1.6.1
   Compiling semver-parser v0.7.0
   Compiling dtoa v0.4.6
   Compiling strsim v0.8.0
   Compiling mime v0.3.16
   Compiling ansi_term v0.11.0
   Compiling ascii v0.9.3
   Compiling vec_map v0.8.2
   Compiling ipnet v2.3.0
   Compiling regex-syntax v0.6.21
   Compiling base64 v0.12.3
   Compiling linked-hash-map v0.5.3
   Compiling termcolor v1.1.0
   Compiling hex v0.4.2
   Compiling tracing-core v0.1.17
   Compiling thread_local v1.0.1
   Compiling unicase v2.6.0
   Compiling proc-macro-error-attr v1.0.4
   Compiling proc-macro-error v1.0.4
   Compiling error-chain v0.12.4
   Compiling futures-channel v0.3.8
   Compiling indexmap v1.6.0
   Compiling miniz_oxide v0.4.3
   Compiling num-traits v0.2.14
   Compiling num-integer v0.1.44
   Compiling unicode-bidi v0.3.4
   Compiling tinyvec v1.0.1
   Compiling form_urlencoded v1.0.0
   Compiling futures-task v0.3.8
   Compiling http v0.2.1
   Compiling pest v2.1.3
   Compiling unreachable v1.0.0
   Compiling heck v0.3.1
   Compiling textwrap v0.11.0
   Compiling addr2line v0.14.0
   Compiling unicode-normalization v0.1.15
   Compiling tracing v0.1.21
   Compiling want v0.3.0
   Compiling aho-corasick v0.7.15
   Compiling semver-parser v0.10.1
   Compiling quote v1.0.7
   Compiling http-body v0.3.1
   Compiling jobserver v0.1.21
   Compiling net2 v0.2.35
   Compiling iovec v0.1.4
   Compiling num_cpus v1.13.0
   Compiling socket2 v0.3.16
   Compiling atty v0.2.14
   Compiling time v0.1.44
   Compiling dirs-sys v0.3.5
   Compiling subprocess v0.2.6
   Compiling security-framework-sys v2.0.0
   Compiling core-foundation v0.9.1
   Compiling combine v3.8.1
   Compiling idna v0.2.0
   Compiling mime_guess v2.0.3
   Compiling regex v1.4.2
   Compiling cc v1.0.62
   Compiling rand_core v0.5.1
   Compiling mio v0.6.22
   Compiling clap v2.33.3
   Compiling dirs v3.0.1
   Compiling backtrace v0.3.54
   Compiling security-framework v2.0.0
   Compiling url v2.2.0
   Compiling rand_chacha v0.2.2
   Compiling tokio v0.2.23
   Compiling libz-sys v1.1.2
   Compiling openssl-sys v0.9.58
   Compiling libssh2-sys v0.2.19
   Compiling libgit2-sys v0.12.14+1.1.0
   Compiling chrono v0.4.19
   Compiling env_proxy v0.4.1
   Compiling synstructure v0.12.4
   Compiling rand v0.7.3
   Compiling toml_edit v0.2.0
   Compiling tokio-util v0.3.1
   Compiling pin-project-internal v1.0.1
   Compiling structopt-derive v0.4.13
   Compiling tempfile v3.1.0
   Compiling pin-project v1.0.1
   Compiling structopt v0.3.20
   Compiling pin-project v0.4.27
   Compiling failure v0.1.8
   Compiling futures-util v0.3.8
   Compiling tracing-futures v0.2.4
   Compiling tokio-tls v0.3.1
   Compiling h2 v0.2.7
   Compiling semver v0.10.0
   Compiling serde_urlencoded v0.6.1
   Compiling toml v0.5.7
   Compiling semver v0.11.0
   Compiling hyper v0.13.9
   Compiling cargo_metadata v0.11.4
   Compiling hyper-tls v0.4.3
   Compiling reqwest v0.10.8
   Compiling git2 v0.13.12
   Compiling cargo-edit v0.7.0
    Finished release [optimized] target(s) in 3m 15s
  Installing /Users/yu/.cargo/bin/cargo-add
  Installing /Users/yu/.cargo/bin/cargo-rm
  Installing /Users/yu/.cargo/bin/cargo-upgrade
   Installed package `cargo-edit v0.7.0` (executables `cargo-add`, `cargo-rm`, `cargo-upgrade`)
```

VS Code で [Rust](vscode:extension/rust-lang.rust) 拡張機能をインストールする
