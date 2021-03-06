# Rust on balena - Hello world!

This is a very simple project that is an example of how to build and run Rust
code on a device that is supported by [balena](https://balena.io).
It showcases how to create a multi-staged build process, that results in an
app image that does not have compilation tools embedded.

## Multi-staged build process; using Dockerfile.template

[Dockerfile.template](Dockerfile.template) file builds artifacts in release
mode with optimizations by default and the final image does not contain
build tools, Rust toolchain or the application source code. It contains
the application binary only.

This sample application depends on the [clap](https://crates.io/crates/clap)
crate intentionally to demonstrate build artifacts caching.

## Push to a device

Start an image build on a local-mode balena device:

```sh
balena push $DEVICE_IP -s .
```

## Documentation

* [`balena push` command](https://www.balena.io/docs/reference/cli/#push-applicationordevice)
* [Develop locally](https://www.balena.io/docs/learn/develop/local-mode/)
