# ThinkPad-E480-Hackintosh

为ThinkPad E480提供的黑苹果EFI (OpenCore)。

## 电脑配置

|规格|详细信息|
|-|-|
|型号|Lenovo ThinkPad E480 (20KNA04VCD)|
|处理器|Intel Core i5-8250U|
|内存|8GB DDR4 2400MHz|
|固态硬盘|SKhynix HFM128GDHTNG-8310B 128G|
|机械硬盘|WDC WD10SPZX-08Z10 1TB|
|集成显卡|Intel UHD Graphics 620|
|独立显卡|AMD Radeon RX 550 (2GB)|
|声卡|Conexant CX20753/4 (节点:15)|
|有线网卡|Realtek R8111GUS|
|无线网卡|Realtek RTL8821CE -> BCM94352Z (DW1560)|

## 支持系统

理论支持最新的macOS Ventura。

已测试：
- macOS Monterey 12.6.3
- macOS Ventura 13.2.1

## 工作正常

- CPU：驱动、变频正常。

- 硬盘：工作正常。

- 集成显卡：已伪装为`Intel HD Graphics 620`，将显存设置为3072MB。支持HDMI `2K@60Hz`、`1080P@60Hz`。

- 声卡：注入ID:15，工作正常。

- 有线网卡：工作正常。

- USB：读写文件、数据传输正常。

- 键盘：PrtSc已映射为F13，工作正常。

- 触摸板：工作正常。

- 小红点：工作正常。

- 摄像头：工作正常。

## 工作异常

- 独立显卡：无法正常驱动，已屏蔽。

- 无线网卡：`Realtek RTL8821CE`无法正常驱动，且无解。建议更换为：`BCM94352Z (DW1560)`或其他免驱的网卡(可自行搜索)。
  > 不推荐BCM94350ZAE (DW1820A)

- 蓝牙：同无线网卡。更换后正常工作。

## 已知Bug

- <kbd>Fn</kbd>在睡眠唤醒后无法正常工作。

- 电池在睡眠唤醒后插拔电源，电量、电池状态可能不更新。可通过手动睡眠解决。

## 注意事项：

1. 请先使用通用镜像安装macOS，完成后再替换该EFI。

2. 推荐在安装前在BIOS中更改如下：

- Security
  - Secure Boot > Secure Boot: Disabled
  - Intel(R) SGX > Intel (R) SGX Control: Disabled

- Startup
  - UEFI/Legacy Boot: Both
  - UEFI/Legacy Boot Priority: UEFI First
  - Optional Key Display: Enabled

- Config
  - Storage > Controller Mode: AHCI mode

3. 已注入`MacBook Pro 2019`的三码，但仍建议自己生成三码。

## 更新

### 2023-02-18
OpenCore版本: 0.8.9
- 初次上传。
