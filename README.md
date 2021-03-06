<div align="center">
<img src="https://cdn.jsdelivr.net/gh/TokiharaSay/Pic/Hackintosh/MSI-B360M-MORTAR-Hackintosh.jpg" width="350px">
</div>

<h1 align="center">MSI-B360M-MORTAR-Hackintosh</h1>
<h3 align="center">微星 B360M迫击炮 黑苹果 OpenCore 引导配置</h3>
<br>

## Disclaimer / 免责声明

Your warranty is now void. Please do some research if you have any concerns before utilizing my project. I am not responsible for any loss, including but not limited to Kernel Panic, device fail to boot or can not function normally, storage damage or data loss, atomic bombing, World War III, The CK-Class Restructuring Scenario that SCP Foundation can not prevent, and so on.

你的保修将完全失效。如果您有任何疑虑，请在使用我的项目之前先进行一些研究。我对任何损失均不负责，包括但不限于 Kernel Panic、设备无法启动或无法正常工作、硬件损坏或数据丢失、原子弹爆炸、第三次世界大战、SCP 基金会无法避免的 CK 级现实重构等。

Please choose the branch you need for different graphics cards

不同显卡请选择你需要的分支


## Hardware Specifications / 硬件配置

| Specifications | Details |
|:---|:---|
| Computer Model | MSI-B360M-MORTAR |
| CPU | Intel Core i5-8400 |
| Memory | DDR4 2666 Mhz. 8 GB |
| NVMe SSD | SAMSUNG 970 EVO 250G |
| Integrated Graphics | Intel UHD Graphics 630 |
| Wireless Card | Manually  to PCIE Card BCM943602CDP  |

## Working & Not Working / 可用与不可用的功能

### Non-Fuctional / 不工作

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Non-Fuctional<br>没有不工作 | ✅ |  | Completely normal<br>完全正常 |


### Video and Audio / 音频与视频

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| Full Graphics Accleration (QE/CI)<br>图形硬件加速 | ✅ | `WhateverGreen.kext` | |
| Audio Recording via 3.5mm microphone<br>通过3.5mm 麦克风录音 | ✅ | `AppleALC.kext` | |
| Audio Playback after through 3.5mm<br>通过 后 3.5mm 接口播放音频 | ✅ | `AppleALC.kext` | |
| Automatic Headphone Output Switching<br>当插入耳机时自动切换音频输出 | ✅ | `AppleALC.kext` | |


### Power, Charge, Sleep and Hibernation / 电源管理、充电、睡眠、休眠

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| CPU Power Management (SpeedShift)<br>CPU 电源管理 | ✅ | `SSDT-PLUG` | Use `Macmini8,1` for beter power management<br>使用 `Macmini8,1` 机型以获得更好的电源管理 |
| NVMe Drive Battery Management<br>NVMe 硬盘电源管理 | ✅ | `NVMeFix.kext` | |
| S3 Sleep / Hibernation Mode 3<br>S3 睡眠 / Mode 3 休眠 | ✅ | 


### Input & Output

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| WiFi | ✅ | `AirportFixup.kext` | Suggest to switch Broadcom based card<br>推荐更换博通无线网卡 |
| USB 2.0, USB 3.0 | ✅ | `USBPorts.kext` | |

### Display, TrackPad and Keyboard / 显示器、触摸板和键盘

| Feature | Status | Dependency | Remarks |
| --- | --- | --- | --- |
| HiDPI | ✅ | | Natively enabled on UHD DP  screen external<br>在 UHD DP 4K 外接屏幕上原生启用 |

## Refrence / 必读参考资料

- [dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [dortania's OpenCore Post Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania Getting Started with ACPI](https://dortania.github.io/OpenCore-Post-Install/)
- [dortania opencore multiboot](https://github.com/dortania/OpenCore-Multiboot)
- [WhateverGreen Intel HD Manual](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md)
- `Configuration.pdf` and `Differences.pdf` in each OpenCore releases.
- [daliansky/OC-little](https://github.com/daliansky/OC-little)
- [OpenCore 简体中文参考手册 (非官方)](https://oc.skk.moe)

**No seriously, PLEASE read those.**

**务必阅读上述参考资料**

## Requirement / 需求和依赖

### Basic / 基本需求

- A macOS machine (optional): to create the macOS installer and build the EFI.
  一台已经安装好 macOS 的机器，用于制作 macOS 安装器和编译本项目
- Flash drive, 12GB or more, for the above purpose.
  一个容量大于等于 12 GiB 的 U 盘
- [PlistEDPlus](https://github.com/ic005k/PlistEDPlus) to edit plist files on Windows.
  编辑 plist 文件的工具 [PlistEDPlus](https://github.com/ic005k/PlistEDPlus)
- [MaciASL](https://github.com/acidanthera/MaciASL) for patching ACPI tables and editing ACPI patches.
  用于修补和编辑 ACPI 的工具 [MaciASL](https://github.com/acidanthera/MaciASL)
- [MountEFI](https://github.com/corpnewt/MountEFI) to quickly mount EFI partitions under macOS.
  在 macOS 下挂载 EFI 分区的工具 [MountEFI](https://github.com/corpnewt/MountEFI)
- [IORegistryExplorer](https://developer.apple.com/downloads) for diagnosis.
  用于诊断的 [IORegistryExplorer](https://developer.apple.com/downloads)
- [HackinTool](https://github.com/headkaze/Hackintool) for diagnosis ONLY. Most of the built-in patches are outdated.
  **仅用于** 诊断的 [HackinTool](https://github.com/headkaze/Hackintool)，大部分内置的补丁和工具已经过时、不再适用
- Patience and time, especially if this is your first time Hackintosh-ing.
  耐心和时间。如果你是第一次进行黑苹果，这尤为重要

### Hardware Modification / 硬件修改

#### SSD

Samusung PM981 is not supported AT ALL. Make sure to switch at least one SSD.

三星 PM981 **完全** 无法使用，务必更换至少一块 SSD 硬盘。


#### Wireless Card / 无线网卡

it is recommended to use Broadcom wireless network card for the best experience (better, refer to the use of the best experience).

建议使用博通无线网卡以获得 **更好** 的体验（更好，指使用 **体验**）。


### Update or Downgrade BIOS Version / 升级或降级 BIOS

It is recommended to use a specific version of the BIOS for the best use experience. The most recommended BIOS version is E7B23IMS.1B0

推荐使用特定版本的 BIOS 以获得最佳的使用体验。最推荐 BIOS 版本是 E7B23IMS.1B0



[Download BIOS at MSI Support Website. 从微星支持网站下载 BIOS。](https://www.msi.com/Motherboard/support/B360M-MORTAR)

### BIOS Settings / 修改 BIOS 设置

- Settings > Advanced > integrated graphics card multi display: allow
- Settings > Advanced > ERP ready: allow
- Settings > Advanced > Windows operating system configuration > secure boot > MSI quick boot: off
- Settings > Advanced > Windows operating system configuration > secure boot > fast boot: off
- Settings > Advanced > Windows operating system configuration > secure boot > secure boot: off
- Settings > Advanced > wake up event Settings > USB device wake up from S3 / S4 / S5: allow
- OC > CPU features > CFG lock: Disable

## Other Information / 其它信息

### How to build EFI / 如何编译本 EFI

There is no prebuilt version of EFI avaliable YET, and it is only able to build under macOS. Use a virtual machine or [action-tmate](https://github.com/mxschmitt/action-tmate) if you have to.

本 EFI **暂时不提供** 预编译版本，并且编译必须在 macOS 下进行。如有必要，请使用虚拟机、或通过 [action-tmate](https://github.com/mxschmitt/action-tmate) 将 GitHub Action 作为 macOS VPS 使用。

Use following command to build the EFI.

使用下述指令编译 EFI：

```bash
git clone https://github.com/TokiharaSay/OpenCore-MSI-B360M-MORTAR-Hackintosh
cd OpenCore-MSI-B360M-MORTAR-Hackintosh
chmod +x **/*.sh
./build.sh
```

Find generated EFI under `Output` folder. Find OpenCore config at `Output/EFI/OC/config_sample.plist` and fill in your own SMBIOS (Follow [the guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html), use model `MacBookPro14,3`) then rename `config_sample.plist` to `config.plist`.

你可以在 `Output` 目录下找到生成的 EFI。OpenCore 配置文件路径为 `Output/EFI/OC/config_sample.plist`，你需要自行生成 SMBIOS 信息（遵循 [这篇教程](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html) 的步骤，使用机型 `Macmini8,1`）并填入配置文件中，然后将 `config_sample.plist` 重命名为 `config.plist`。

----

Use following command to update and rebuild the EFI from upstream.

使用下述指令从上游更新和重新编译 EFI：

```bash
cd OpenCore-MSI-B360M-MORTAR-Hackintosh
git pull --rebase
chmod +x **/*.sh
./build.sh
```

Everytime you rebuilt the EFI you have to fill in the SMBIOS again. So keep your SMBIOS info saved in a safe place!

每次重新编译 EFI 后你都需要重新填入一次 SMBIOS 信息，所以务必将你的 SMBIOS 信息保存在一个安全的位置！

### Directories Structure / 项目目录结构

```
.
├── ACPI
│   ├── OEM_DSDT # The original DSDT dissembled from OEM BIOS
│   └── SSDT
│       ├── DSL # SSDT source dsl files
│       └── build_acpi.sh # dsl files build script
├── Config
│   └── config_sample.plist # Sample config.plist
├── Kexts
│   ├── Local # Kexts files where there is no way to be downloaded
│   │   ├── ThunderboltReset.kext
│   │   ├── USBMap.kext
│   │   └── XHCI-unsupported.kext
│   └── download_kexts.sh # Use the script to download the rest of the kexts
├── LICENSE
├── OpenCore
│   ├── OldSample.plist # The curent version of OpenCore sample. Used to diff the configuration when update OpenCore to a newer version 
│   └── oc.sh # Script uesd to download OpenCorePkg and construct EFI folder
├── README.md # The file you are currently reading
└── build.sh # Overall build script, will call all the scripts mentioned above.
```

## Donation / 捐赠

Donating to this project is OPTIONAL. But feel free to buy me a coffee if you appreciate my works.

捐赠本项目 **并不是必需的**。但是如果我的项目对你有所帮助，为什么不考虑一下给我买杯咖啡呢？



## Maintainer / 维护者

**MSI-B360M-MORTAR** © [TokiharaSay](https://github.com/TokiharaSay), Released under the [GPL-3.0](./LICENSE) License.<br>
Authored and maintained by TokiharaSaywith help from contributors ([list](https://github.com/TokiharaSay/OpenCore-MSI-B360M-MORTAR-Hackintosh/graphs/contributors)).

>[Blog](https://blog.runebalot.cn/) · GitHub [@TokiharaSay](https://github.com/TokiharaSay) · Telegram Channel [@TokiharaSayChannel](https://t.me/TokiharaSay) · Twitter [@TokiharaSay](https://twitter.com/TokiharaSay) 
