# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.0.14] - 2022-05-26

### Changed

- Update to OnnxRuntime v1.11.0
- support aarch64 architecture
- support specify architecture

Compile aarch64 cross-platform in linux_x64

```bash
export ORT_STRATEGY="system"
export ORT_LIB_LOCATION="/home/rust/src/onnxruntime-linux-aarch64-1.11.0"
export LD_LIBRARY_PATH=/home/rust/src/onnxruntime-linux-aarch64-1.11.0/lib:$LD_LIBRARY_PATH
export BINDGEN_EXTRA_CLANG_ARGS="--target=aarch64-unknown-linux-gnu --sysroot=/usr/aarch64-linux-gnu -I/usr/aarch64-linux-gnu/include"
export ORT_TARGET_ARCH="aarch64"
# cargo build --release
```

## [0.0.14] - 2021-08-01

### Changed

- Update to OnnxRuntime v1.8.1

## [0.0.13] - 2021-08-01

### Changed

- Update to OnnxRuntime v1.7.0

## [0.0.12] - 2021-04-11

### Added

- Add `String` datatype ([#58](https://github.com/nbigaouette/onnxruntime-rs/pull/58))
- Initial support for Apple M1 ([#74](https://github.com/nbigaouette/onnxruntime-rs/pull/74))

### Changed

- Fix Windows i686 compilation ([#70](https://github.com/nbigaouette/onnxruntime-rs/pull/70))
- Upgrade dependencies ([#75](https://github.com/nbigaouette/onnxruntime-rs/pull/75))

## [0.0.11] - 2021-02-22

### Changed

- Prevent session from being built a temporary environment resulting in segfault ([#46](https://github.com/nbigaouette/onnxruntime-rs/pull/46))
- Update onnxruntime to 1.6.0 ([#59](https://github.com/nbigaouette/onnxruntime-rs/pull/59))

### Added

- Run CI on more platforms ([#34](https://github.com/nbigaouette/onnxruntime-rs/pull/34))
- Re-export `ndarray` for better ergonomics ([#45](https://github.com/nbigaouette/onnxruntime-rs/pull/45))
- Add `with_model_from_memory()` to load a model from memory ([#36](https://github.com/nbigaouette/onnxruntime-rs/pull/36))

## [0.0.10] - 2020-10-28

### Changed

- Update ONNX Runtime to 1.5.2 from 1.4.0 ([#30](https://github.com/nbigaouette/onnxruntime-rs/pull/30))
- Refactor feature flags and how bindings are generated ([#31](https://github.com/nbigaouette/onnxruntime-rs/pull/31))
- Refactor build script for better cross-platform support, including Windows support ([#33](https://github.com/nbigaouette/onnxruntime-rs/pull/33))

## [0.0.9] - 2020-10-13

### Added

- Added a changelog ([#26](https://github.com/nbigaouette/onnxruntime-rs/pull/26))
- Integrate Runtime's logging with rust's `tracing` logging ([#21](https://github.com/nbigaouette/onnxruntime-rs/pull/21))
- Update `ureq` used to download pre-trained models, fixing download problem ([algesten/ureq#179](https://github.com/algesten/ureq/issues/179)).
- Properly support inputs with dynamic dimensions ([#23](https://github.com/nbigaouette/onnxruntime-rs/pull/23))

## [0.0.8] - 2020-08-26

### Added

- Use ONNX Runtime 1.4.0

## [0.0.7] - 2020-08-26

### Added

- Use `tracing` crate instead of `log` ([#19](https://github.com/nbigaouette/onnxruntime-rs/pull/19))
- Add integration tests ([#17](https://github.com/nbigaouette/onnxruntime-rs/pull/17))
- Add possibility to download most pre-trained models available from [ONNX Zoo](https://github.com/onnx/models) ([#16](https://github.com/nbigaouette/onnxruntime-rs/pull/16))

## [0.0.6] - 2020-08-14

### Added

- Add feature to download pre-trained pre-trained models available from [ONNX Zoo](https://github.com/onnx/models) ([#15](https://github.com/nbigaouette/onnxruntime-rs/pull/15))
- Add coded coverage measurement ([#13](https://github.com/nbigaouette/onnxruntime-rs/pull/13))
- API renames and cleanups

## [0.0.5] - 2020-08-9

### Added

- Initial working version

[unreleased]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.12...HEAD
[0.0.12]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.11...v0.0.12
[0.0.11]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.10...v0.0.11
[0.0.10]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.9...v0.0.10
[0.0.9]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.8...v0.0.9
[0.0.8]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.7...v0.0.8
[0.0.7]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.6...v0.0.7
[0.0.6]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.5...v0.0.6
[0.0.5]: https://github.com/nbigaouette/onnxruntime-rs/compare/v0.0.4...v0.0.5
