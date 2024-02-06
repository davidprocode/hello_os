**main ref: https://os.phil-opp.com/freestanding-rust-binary/**

- for add embedded ARM system as target

```bash
  rustup target add thumbv7em-none-eabihf
```

- for crate builds as a ARM system executable

```bash
  cargo build --target thumbv7em-none-eabihf
```

- for crate builds as a freestanding executable on Linux

```bash
  cargo rustc -- -C link-arg=-nostartfiles
```

- for crate builds as a freestanding executable on Windows

```bash
cargo rustc -- -C link-args="ENTRY:_start SUBSYSTEM:console"
```

- for crate builds as a freestanding executable on MacOS

```bash
cargo rustc -- -C link-args="-e __start -static -nostartfiles"
```

- for crate builds as a custom kernel

```bash
cargo build --target x86_64-hello_os.json
```
