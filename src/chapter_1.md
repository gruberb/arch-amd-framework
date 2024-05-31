# Preparation 

Before we start setting up Arch on the AMD Framework 13" laptop, we have to create a bootable USB stick with the latest Arch ISO on it. Depending on your operating system at hand, this step will vary. Throughout the chapters, it is highly recommended to always check out the [Arch Wiki](https://wiki.archlinux.org/) for deeper insights and up-to-date information:

- [macOS: Create a bootable USB stick](https://wiki.archlinux.org/title/USB_flash_installation_medium#In_macOS)
- [Linux: Create a bootable USB stick](https://wiki.archlinux.org/title/USB_flash_installation_medium#In_GNU/Linux)

Since this is also a personal note taking, I will lay out how to do it for macOS.

1. You need a USB stick which is at least as big as the ISO File, which is as of today [2024-05-31] around 1.1GB.
2. Download the latest [ISO image](https://archlinux.org/download/).
3. Plug in the USB stick and check it's path: `diskutil list`
4. Unmount the USB stick: `diskutil unmountDisk /dev/diskX`
5. Copy the ISO to the stick: `dd if=path/to/archlinux-version-x86_64.iso of=/dev/rdiskX bs=1m`

#### Summary

```bash
$ diskutil list
$ diskutil unmountDisk /dev/diskX
$ dd if=path/to/archlinux-version-x86_64.iso of=/dev/rdiskX bs=1m
```

