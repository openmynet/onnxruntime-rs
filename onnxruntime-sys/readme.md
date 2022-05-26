# 构建 onnxruntime-sys

## 下载 onnxruntime 库

## 构建 onnxruntime-sys 对应的 bindings

> 当前支持的构建仅针对 onnxruntime v1.11.0 版本

```bash
#------------WINDOWS--------
$env:ORT_STRATEGY="system"
$env:ORT_LIB_LOCATION="../libs/onnxruntime-linux-x64-1.11.0"
# windows x86
cargo build --features generate-bindings --target i686-pc-windows-msvc
# windows x64
cargo build --features generate-bindings --target x86_64-pc-windows-msvc

#------------LINUX--------
docker run --rm -it -v "${pwd}:/home/rust/src" rust:1.58.1-bullseye
sed -i 's#http://deb.debian.org#https://mirrors.163.com#g' /etc/apt/sources.list
sed -i 's#http://security.debian.org#https://mirrors.163.com#g' /etc/apt/sources.list
apt update && apt upgrade -y
export ORT_STRATEGY=system
export ORT_LIB_LOCATION="/home/rust/src/libs/onnxruntime-linux-x64-1.11.0"
apt install clang -y


docker run --rm -it -v "${pwd}:/home/rust/src" rust:1.58.1-bullseye

# linux x64
cargo build --features generate-bindings --target x86_64-unknown-linux-gnu

# linux x86
apt install gcc-i686-linux-gnu -y
export BINDGEN_EXTRA_CLANG_ARGS="--target=gcc-i686-linux-gnu --sysroot=/usr/i686-linux-gnu -I/usr/i686-linux-gnu/include"
export ORT_TARGET_ARCH="x86"
cargo build --features generate-bindings --target i686-unknown-linux-gnu

# linux aarch64-arm64
apt install gcc-aarch64-linux-gnu
export BINDGEN_EXTRA_CLANG_ARGS="--target=aarch64-unknown-linux-gnu --sysroot=/usr/aarch64-linux-gnu -I/usr/aarch64-linux-gnu/include"
export ORT_TARGET_ARCH="aarch64"
cargo build --features generate-bindings --target aarch64-unknown-linux-gnu

#------------OSX--------
# 需要在OSX系统下进行操作

export ORT_TARGET_ARCH="aarch64"
cargo build --features generate-bindings --target aarch64-apple-darwin

export ORT_TARGET_ARCH="x86_64"
cargo build --features generate-bindings --target x86_64-apple-darwin

```

## 测试

cargo run --example c_api_sample
