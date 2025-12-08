# MicroPython Custom Builder

Automated GitHub Actions workflow for building MicroPython firmware.

## Features

- Automatic release detection (checks every 6 hours)
- Builds for multiple targets:
  - **Windows** (32-bit, 64-bit)
  - **RP2** (Pico, Pico W, Pico 2)
  - **ESP8266** (512K, 1M, 2M+ flash variants)
- Efficient caching (toolchains, mpy-cross)
- Automatic GitHub releases with binaries

## Supported Targets

| Target | Boards/Variants | Output |
|--------|-----------------|--------|
| Windows | i686, x86_64 | `.exe` |
| RP2 | RPI_PICO (RP2040) | `.uf2` |
| ESP8266 | 2M, FLASH_1M, FLASH_512K | `.bin` |

## Usage

### Automatic builds

The workflow automatically checks for new MicroPython releases every 6 hours. When a new release is detected, it triggers a full build and creates a corresponding release in this repository.

### Manual builds

1. Go to **Actions** > **Build MicroPython**
2. Click **Run workflow**
3. Configure options:
   - `mp_version`: Version tag (e.g., `v1.26.1`) or `latest`
   - `targets`: Comma-separated list (`windows,rp2,esp8266`)
   - `upload_release`: Create GitHub release with binaries

## Downloads

Pre-built binaries are available in [Releases](../../releases).

## License

This project only contains build automation. MicroPython itself is licensed under the MIT license.
