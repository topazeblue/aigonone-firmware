# AigonOne Firmware

Pre-built firmware binaries for M5Stack Core2 devices.

## Releases

Each release folder contains:

```
m5stack/
├── releases.txt              # Available versions (newest first)
└── v0.2rc3-dev-045/
    ├── manifest.json         # ESP Web Tools format (for flashing)
    ├── release.json          # Metadata (version, date, sha256, etc.)
    ├── bootloader.bin        # 0x1000
    ├── partitions.bin        # 0x8000
    ├── boot_app0.bin         # 0xe000
    └── firmware.bin          # 0x10000
```

## Web Flash

Use the web flasher at [a1.aigon.ai/flash](https://a1.aigon.ai/flash)

The `manifest.json` is compatible with [ESP Web Tools](https://esphome.github.io/esp-web-tools/).

## Manual Flash

```bash
esptool.py --chip esp32 --port /dev/tty.usbserial-XXXXX \
    write_flash 0x1000 bootloader.bin \
                0x8000 partitions.bin \
                0xe000 boot_app0.bin \
                0x10000 firmware.bin
```
