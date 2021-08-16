---
title: Windows 10 设备的装载工具和方法
description: 载入Windows 10设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器
keywords: 载入Windows 10设备， 组策略， 终结点配置管理器， 移动设备管理， 本地脚本， gp， sccm， mdm， intune
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
ms.openlocfilehash: 253c055198547852c55a44b60910e3a38229737e89fa5e2fa467e74089ee20d6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863795"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-in-defender-for-endpoint"></a>适用于 Defender for Endpoint 中 Windows 10设备的载入工具和方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365DLP (终结点数据丢失) ](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365内部风险管理](/microsoft-365/compliance/insider-risk-management)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

必须配置组织中设备，以便 Defender for Endpoint 服务可以从这些设备获取传感器数据。 可以使用多种方法和部署工具来配置贵组织的设备。

支持以下部署工具和方法：

- 组策略
- Microsoft Endpoint Configuration Manager
- 移动设备管理 (包括Microsoft Intune) 
- 本地脚本

## <a name="in-this-section"></a>本节内容

主题|说明
:---|:---
[使用Windows 10载入设备](configure-endpoints-gp.md)|使用组策略在设备上部署配置包。
[使用Windows载入Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|可以使用 Microsoft Endpoint Manager () 版本 1606 或 Microsoft Endpoint Manager (current branch) 版本 1602 或更早版本在设备上部署配置包。
[使用移动设备管理工具载入 Windows 10 设备](configure-endpoints-mdm.md)|使用移动设备管理工具或Microsoft Intune在设备上部署配置包。
[使用本地脚本载入 Windows 10 设备](configure-endpoints-script.md)|了解如何使用本地脚本在终结点上部署配置包。
[载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)|了解如何使用配置包配置 VDI 设备。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)。
