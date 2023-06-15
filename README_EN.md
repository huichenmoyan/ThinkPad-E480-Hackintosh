<div align="center">
<img src="https://img.skk.moe/2020/02/01/15deff1c-62cc-45b9-aac2-2f6bb9a4350b.jpg" width="350px">
  
[简体中文](README.md) | English
</div>

# ThinkPad-E480-Hackintosh

Providing Hackintosh EFI for ThinkPad E480 (OpenCore)。

## Devices

|Specifications|Details|
|-|-|
|Computer Model|Lenovo ThinkPad E480 (20KNA04VCD)|
|CPU|Intel Core i5-8250U|
|Memory|8GB DDR4 2400MHz|
|NVMe SSD|SKhynix HFM128GDHTNG-8310B 128G|
|HDD|WDC WD10SPZX-08Z10 1TB|
|Integrated Graphics|Intel UHD Graphics 620|
|Discrete Graphics|[Blocked]AMD Radeon RX 550 (2GB)|
|Sound Card|Conexant CX20753/4 (layout-id:15)|
|Ethernet|Realtek R8111GUS|
|Wireless Card|Realtek RTL8821CE -> BCM94352Z (DW1560)|

## Supported Systems

Supports macOS Ventura
> Although it can run macOS Sonoma, it can't drive wireless card.

Tested on：

- macOS Monterey 12.6.3
- macOS Ventura 13.2.1
- macOS Ventura 13.3
- macOS Ventura 13.4

## What is working

- CPU：XCPM power management is native supported. HWP is fully enabled as well.

- Hard Disk：It works well.

- Display：It has been faked to`Intel HD Graphics 620`, VRAM has been set to 3072MB. The HDMI supports `HDMI 2K@60Hz` & `1080P@60Hz`.

- Audio: It injects `layout-id: 15` and works well.

- Ethernet: It works well.

- USB：It works well.

- Keyboard: PrtSc has been changed to F13 and works well.

- Trackpad & Trackpoint: They work well.

- Camera：It works well.

## What is not working

- Discrete Graphics: It can't work and has been blocked.

- Wireless Card：The built-in Wireless Card `Realtek RTL8821CE` can't drive well.

- Bluetooth: As the Wireless Card, can't work well.

## Known issues

- <kbd>Fn</kbd> can't work after waking from sleep.

## Tips

1. Please use the universal image to install macOS, then replacing the EFI.

2. It is recommended to change the BIOS settings like this：

- Security
  - Secure Boot > Secure Boot: Disabled
  - Intel(R) SGX > Intel SGX: Disabled

- Startup
  - UEFI/Legacy Boot: Both
  - UEFI/Legacy Boot Priority: UEFI First
  - Optional Key Display: Enabled

- Config
  - Storage > Controller Mode: AHCI mode

## Updates

### 2023-06-15
OpenCore: 0.9.2
- Update OpenCore
- Update Kexts

### 2023-02-18
OpenCore: 0.8.9
- Update for the first time.

## Screenshots

![图片](https://user-images.githubusercontent.com/65167412/219908060-64258a9c-de23-4fb4-b590-dd35989c57f3.png)

![图片](https://user-images.githubusercontent.com/65167412/219908090-a21a9a7f-a8e2-4354-905f-701dc8978fd7.png)

![图片](https://user-images.githubusercontent.com/65167412/219908105-016aa70d-f014-4c8d-a0c1-8bfd7836a1d1.png)

![图片](https://user-images.githubusercontent.com/65167412/219908160-77dabe60-b898-42dd-9043-0040800f16af.png)
