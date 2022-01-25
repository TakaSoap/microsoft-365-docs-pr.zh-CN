---
title: 设备要求
description: 设备使用软件的最低硬件和软件要求Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 5fb600434c8f6d7b62e7fd7408c3567a34c0eda0
ms.sourcegitcommit: bcea69bacd1b48827bd60af2880909593a1609a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62202049"
---
# <a name="device-requirements"></a>设备要求

Microsoft 托管桌面定期评估要包含在服务中的设备要求。 本文介绍设备必须满足的硬件和软件要求才能使用Microsoft 托管桌面。 你可以根据这些要求查看已批准用于服务的特定设备的列表。 筛选Microsoft 托管桌面[购买商业Windows Pro站点上的筛选器](https://www.microsoft.com/en-us/windows/business/devices)

> [!NOTE]
> 这些要求可能随时更改，但我们会提前 30 天通知任何硬件要求更改。 最近更改的要求标有 <b>\*</b> 。 

## <a name="check-hardware-requirements"></a>检查硬件要求

除了查看设备规格之外，您还可以使用可下载的准备情况评估检查[](../get-ready/readiness-assessment-downloadable.md)器验证给定设备是否满足必要的要求。 此工具还会检查网络设置以及使服务正常工作所需的终结点。

## <a name="minimum-requirements"></a>最低要求

若要在 Microsoft 托管桌面中注册，设备必须满足或超过所有这些要求。

### <a name="manufacturer"></a>制造商

设备必须由以下制造商之一制造：

- Dell
- HP
- 联想
- Microsoft

> [!NOTE] 
> 从 2022 年 3 月 1 Microsoft 托管桌面，OEM 必须支持由 Microsoft 托管桌面 管理的设备。 与 OEM 合作，了解项目组合中的设备何时将结束使用支持。 客户将负责确保设备在生命周期结束支持之前被替换。 超出 OEM 支持范围的任何设备将继续由 Microsoft 托管桌面 管理，但这些设备的支持可能会受到限制，因为它们面临安全和性能问题的风险，并且我们的服务可能无法缓解这些问题。
</b>

### <a name="installed-software"></a>已安装的软件

设备必须预安装此软件：

- <b>\*</b>Windows 10或Windows 11：Enterprise、Pro 或 Pro Workstation 版本
- 64 位版本的 Microsoft 365 企业应用版 
- 所有适用的设备驱动程序


### <a name="physical-features"></a>物理功能

设备必须具有以下功能：

- 启用 UEFI 安全启动 
- 受信任的平台模块 2.0 
- 具有基于虚拟化的安全性 
- BIOS[支持的虚拟机监控](/windows-hardware/drivers/bringup/device-guard-and-credential-guard)程序保护的代码完整性

有关这些功能以及服务使用的与这些功能相关的技术，请参阅Microsoft 托管桌面[技术](../intro/technologies.md)。

> [!NOTE]
>- ARM处理器不受支持。
>- <b>\*</b>Windows 11具有其他[硬件要求](/windows/whats-new/windows-11-requirements)。

设备应满足或超过以下存储和内存限制：

- 启动驱动器必须是除硬盘外的任何类型。 例如，SSD、NVMe 和 eMMC 驱动器都是有效的选择。
- 启动驱动器的容量必须至少为 128 GB。
- 内部设备内存 (RAM) 必须等于或超过 8 GB。

如果设备是在 2020 年 7 月 1 日之后进行，它还应具有 IR 相机、指纹读取器或两者，以便支持[Windows Hello。](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>推荐的功能

如果你选择具有这些功能的设备，你的用户将拥有更好的体验：

- Intel vPro 平台处理器或 AMD Ryzen Pro处理器
- 容量至少为 256 GB 的 SSD 类型的启动驱动器
- 内部设备内存 (RAM) 至少为 16 GB
- 对现代待机的支持
- 设备为安全核心电脑类型
- 支持内核 DMA 保护
