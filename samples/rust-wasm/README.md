# Rust WASM Example

## Running

```
# Ensure you have the correct target installed
rustup target add wasm32-unknown-unknown
# Produces `target/wasm32-unknown-unknown/release/rust_wasm.wasm`
cargo build --release --target=wasm32-unknown-unknown
# Run Worker
bazel run //src/workerd/server:workerd -- serve ./samples/rust-wasm/config.capnp
```


