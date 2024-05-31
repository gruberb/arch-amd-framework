# Setting up the hard drive

The first step is partitioning the hard drive and installing Linux on it. For this, we need an idea of how the hard drive layout should look like, use a way to encrypt the partitions, and we need an internet connection to do so.

Over the years, I used a combination of different guides to partition Arch. The latest one I adjusted for my own needs [is this one over here](https://github.com/passy1977/Archlinux_Framework13AMD_FullEncryption_TMP2.0_Xfce4/blob/main/README.md). 

> I used to install Arch on Thinkpads, and documented it [in this GitHub repo](https://github.com/gruberb/archive_dotfiles).

## Setting up WiFi

Shortly after you boot, you have to connect to the internet. This can be done through an ethernet connection, but most often than not, it's WiFi. The USB stick ships `iwctl`, which can be used to connect to your network:

```bash
$ iwctl
$ device list
$ station YOURDEVICE scan
$ station YOURDEVICE connect YOURSSID
```

The last command let's you enter your password, and shortly after, you should be connected:
```bash
$ ping archlinux.org
```

## Partitioning

For the layout, I copied it from the guide as is. I am pretty happy about it. But now I am thinking, I should have gotten an external HDD slot for my Framework, so I can switch operating systems more easily. For now, everything is on one hard drive, and I don't create a virtual partition either. 

- EFI       512MB
- /:        100GB
- /home:    850GB

Use `fdisk` to start the partition process.

```bash
$ fdisk /dev/nvme0n1
```

And then the following combination to create the partition shown above:
* Command: g
* Command: n
* Parition number: (default)
* First sector: (default)
* Last sector: 1046529
* Command: t
* Partition type or alias: 1 (set EFI type it's very important)
* Command: n
* Partition number:
* First sector:
* Last sector: 208664577
* Command: n
* Partition number:
* First sector:
* Last sector ...:
* Command: p (check if all partition have a right dimensioning)
* Command: w


