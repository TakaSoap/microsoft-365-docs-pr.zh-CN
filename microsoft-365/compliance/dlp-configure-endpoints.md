---
title: " (预览版的 Windows 10 设备的载入工具和方法) "
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
description: 板载 Windows 10 设备，以便可以将传感器数据发送到 Microsoft 365 合规性解决方案
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769639"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a> (预览版的 Windows 10 设备的载入工具和方法) 

**适用于：**
- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

您的组织中的设备必须配置为 Microsoft 365 终结点数据丢失防护服务可以从这些设备获取传感器数据。 您可以使用多种方法和部署工具来配置组织中的设备。

支持以下部署工具和方法：

- 组策略
- Microsoft Endpoint Configuration Manager
- 移动设备管理 (包括 Microsoft Intune) 
- 本地脚本

## <a name="in-this-section"></a>本节内容
主题 | 说明
:---|:---
[使用组策略的板载 Windows 10 设备](dlp-configure-endpoints-gp.md) | 使用组策略在设备上部署配置包。
[使用 Microsoft 终结点配置管理器的板载 Windows 设备](dlp-configure-endpoints-sccm.md) | 您可以使用 Microsoft 终结点配置管理器 (当前分支) 版本1606或 Microsoft 终结点配置管理器 (当前分支) 版本1602或更早版本，以在设备上部署配置包。
[使用移动设备管理工具的板载 Windows 10 设备](dlp-configure-endpoints-mdm.md) | 使用移动设备管理工具或 Microsoft Intune 在设备上部署配置包。
[使用本地脚本的板载 Windows 10 设备](dlp-configure-endpoints-script.md) | 了解如何使用本地脚本在终结点上部署配置包。
[ (VDI) 设备的板载非永久性虚拟桌面基础结构](dlp-configure-endpoints-vdi.md) | 了解如何使用配置包配置 VDI 设备。
