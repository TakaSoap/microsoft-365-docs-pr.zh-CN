---
title: Windows 10 设备的装载工具和方法
description: 载入 Windows 10 设备，以便它们可以将传感器数据发送到 Microsoft Defender ATP 传感器
keywords: 载入 Windows 10 设备， 组策略， 终结点配置管理器， 移动设备管理， 本地脚本， gp， sccm， mdm， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77b843f9526d8b100845403bc8d2df4bf3259471
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760208"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Windows 10 设备的装载工具和方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 终结点数据丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 预览体验成员风险管理](/microsoft-365/compliance/insider-risk-management)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

必须配置组织中设备，以便 Defender for Endpoint 服务可以从这些设备获取传感器数据。 可以使用多种方法和部署工具来配置贵组织的设备。

支持以下部署工具和方法：

- 组策略
- Microsoft Endpoint Configuration Manager
- 移动设备管理 (包括 Microsoft Intune) 
- 本地脚本

## <a name="in-this-section"></a>本节内容
主题 | 说明
:---|:---
[使用组策略载入 Windows 10 设备](configure-endpoints-gp.md) | 使用组策略在设备上部署配置包。
[使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md) | 可以使用 Microsoft Endpoint Manager (current branch) version 1606 或 Microsoft Endpoint Manager (current branch) version 1602 或更早版本在设备上部署配置包。
[使用移动设备管理工具载入 Windows 10 设备](configure-endpoints-mdm.md) | 使用移动设备管理工具或 Microsoft Intune 在设备上部署配置包。
[使用本地脚本载入 Windows 10 设备](configure-endpoints-script.md) | 了解如何使用本地脚本在终结点上部署配置包。
[载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md) | 了解如何使用配置包配置 VDI 设备。


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
