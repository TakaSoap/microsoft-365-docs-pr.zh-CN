---
title: 适用于移动设备的载入Windows 10工具
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 载入Windows 10设备，以便它们可以将传感器数据发送到 Microsoft 365 合规性解决方案
ms.openlocfilehash: f3f3e6a63b3761209a311ae45fcd20c8a9d786f0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203155"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 设备的装载工具和方法

**适用于：**
- [Microsoft 365DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)

必须配置组织中设备，以便Microsoft 365终结点数据丢失防护服务可以从这些设备获取传感器数据。 可以使用多种方法和部署工具来配置贵组织的设备。

支持以下部署工具和方法：

- 组策略
- Microsoft Endpoint Configuration Manager
- 移动设备管理 (包括Microsoft Intune) 
- 本地脚本

## <a name="in-this-section"></a>本节内容
主题 | 说明
:---|:---
[使用Windows 10载入设备](dlp-configure-endpoints-gp.md) | 使用组策略在设备上部署配置包。
[使用Windows载入设备Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | 可以使用 Microsoft Endpoint Configuration Manager (当前分支) 版本 1606 或 Microsoft Endpoint Configuration Manager (current branch) 版本 1602 或更早版本在设备上部署配置包。
[使用移动设备管理工具载入 Windows 10 设备](dlp-configure-endpoints-mdm.md) | 使用移动设备管理工具或Microsoft Intune在设备上部署配置包。
[使用本地脚本载入 Windows 10 设备](dlp-configure-endpoints-script.md) | 了解如何使用本地脚本在终结点上部署配置包。
[载入非永久虚拟桌面基础结构 （VDI） 设备](dlp-configure-endpoints-vdi.md) | 了解如何使用配置包配置 VDI 设备。