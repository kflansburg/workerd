ARG VARIANT=debian-11
FROM mcr.microsoft.com/devcontainers/base:0-${VARIANT}
USER root

# Install needed packages. Use a separate RUN statement to add your own dependencies.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install build-essential cmake cppcheck valgrind clang lldb llvm gdb libc++-dev libc++abi-dev python3-distutils \
    && apt-get autoremove -y && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install Bazelisk
RUN wget https://github.com/bazelbuild/bazelisk/releases/download/v1.15.0/bazelisk-linux-amd64 \
    && chmod +x bazelisk-linux-amd64 \
    && mv bazelisk-linux-amd64 /usr/local/bin/bazel

# Install Rust
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN rustup target add wasm32-unknown-unknown

ARG USERNAME=vscode
