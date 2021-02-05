---
title: 设备要求
description: 设备使用 Microsoft 托管桌面的最低硬件和软件要求摘要
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110047"
---
# <a name="device-requirements"></a>设备要求

Microsoft 托管桌面会定期评估要包含在服务中的设备要求。 本文介绍了设备必须满足的硬件和软件要求才能使用 Microsoft 托管桌面。 你可以根据这些要求查看已批准用于服务[](device-list.md)的特定设备的列表。

> [!NOTE]
> 这些要求可能会随时更改，但我们会提前 30 天通知任何硬件要求更改。 最近更改的要求标记为 **\*** 。 

## <a name="check-hardware-requirements"></a>检查硬件要求

除了查看设备规格之外，您还可以使用可下载的准备情况评估检查[](../get-ready/readiness-assessment-downloadable.md)器验证给定设备是否满足必要的要求。 此工具还会检查服务正常工作所需的网络设置和终结点。

## <a name="minimum-requirements"></a>最低要求

若要在 Microsoft 托管桌面中注册，设备必须满足或超过所有这些要求。

### <a name="manufacturer"></a>制造商

设备必须由以下制造商之一制造：

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>已安装的软件

设备必须预安装此软件：

- Windows 10 企业版、专业版或专业工作站版
- 64 位版本的Microsoft Office单击即可运行 
- 所有适用的设备驱动程序


### <a name="physical-features"></a>物理功能

设备必须具有以下功能：

- 已启用 UEFI 安全启动 
- 受信任的平台模块 2.0 
- 支持基于虚拟化的安全性 
- 支持虚拟机监控程序保护的代码完整性 

有关这些功能以及服务使用的与这些功能相关的技术，请参阅 [Microsoft 托管桌面技术](../intro/technologies.md)。

> [!NOTE]
> ARM不支持处理器。

设备应满足或超过以下存储和内存限制：

- 启动驱动器必须是除硬盘外的任何类型。 例如，SSD、NVMe 和 eMMC 驱动器都是有效的选择。
- 启动驱动器的容量必须至少为 128 GB。

如果设备是在 2020 年 7 月 1 日之后进行，它还应具有 IR 相机、指纹读取器或两者，以支持[Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>建议的要求

虽然它们不是绝对要求，但如果选择具有这些功能的设备，你的用户将拥有更好的体验：

- Intel vPro 平台处理器或 AMD Ryzen Pro 处理器
- 容量至少为 256 GB 的 SSD 类型的启动驱动器
- 支持新式待机
- 设备为安全核心电脑类型
- 支持内核 DMA 保护
