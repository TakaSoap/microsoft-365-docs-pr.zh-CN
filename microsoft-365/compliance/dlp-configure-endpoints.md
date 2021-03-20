---
title: Windows 10 设备的装载工具和方法
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 载入 Windows 10 设备，以便它们可以将传感器数据发送到 Microsoft 365 合规性解决方案
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917848"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 设备的装载工具和方法

**适用于：**
- [Microsoft 365 终结点数据丢失防护 (DLP) ](./endpoint-dlp-learn-about.md)

必须配置组织中设备，以便 Microsoft 365 终结点数据丢失防护服务可以从这些设备获取传感器数据。 可以使用多种方法和部署工具来配置贵组织的设备。

支持以下部署工具和方法：

- 组策略
- Microsoft Endpoint Configuration Manager
- 移动设备管理 (包括 Microsoft Intune) 
- 本地脚本

## <a name="in-this-section"></a>本节内容
主题 | 说明
:---|:---
[使用组策略载入 Windows 10 设备](dlp-configure-endpoints-gp.md) | 使用组策略在设备上部署配置包。
[使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](dlp-configure-endpoints-sccm.md) | 可以使用 Microsoft Endpoint Configuration Manager (current branch) version 1606 或 Microsoft Endpoint Configuration Manager (current branch) version 1602 或更早版本在设备上部署配置包。
[使用移动设备管理工具载入 Windows 10 设备](dlp-configure-endpoints-mdm.md) | 使用移动设备管理工具或 Microsoft Intune 在设备上部署配置包。
[使用本地脚本载入 Windows 10 设备](dlp-configure-endpoints-script.md) | 了解如何使用本地脚本在终结点上部署配置包。
[载入非持久性虚拟桌面基础结构 (VDI) 设备。](dlp-configure-endpoints-vdi.md) | 了解如何使用配置包配置 VDI 设备。