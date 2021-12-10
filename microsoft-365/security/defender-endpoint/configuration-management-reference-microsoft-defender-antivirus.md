---
title: 管理Microsoft Defender 防病毒中的业务
description: 了解如何使用组策略、Configuration Manager、PowerShell、WMI、Intune 和命令行管理 Microsoft Defender AV
keywords: 组策略， gpo， config manager， sccm， scep， powershell， wmi， intune， defender， 防病毒， 反恶意软件， 安全性， 保护
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 4c73936bd32381988a03ad527a83847497eab71d
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168314"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>管理Microsoft Defender 防病毒中的业务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

可以使用以下工具Microsoft Defender 防病毒和配置自定义设置：

- [Microsoft Intune (](/mem/intune/protect/endpoint-security-antivirus-policy)现在属于Microsoft Endpoint Manager) 
- [Microsoft Endpoint Configuration Manager (](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)现在属于Microsoft Endpoint Manager) 
- [组策略](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI) ](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft 恶意软件保护命令行](./command-line-arguments-microsoft-defender-antivirus.md)实用程序 (称为"mpcmdrun.exe *实用工具*

以下文章提供了使用这些工具管理和配置 Microsoft Defender 防病毒。

|文章|说明|
|:---|:---|
|[使用Microsoft Defender 防病毒和Microsoft Intune管理Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|有关使用 Intune 和 Configuration Manager 部署、管理、报表和配置Microsoft Defender 防病毒|
|[使用Microsoft Defender 防病毒策略设置管理策略](use-group-policy-microsoft-defender-antivirus.md)|ADMX 模板中所有组策略设置的列表|
|[使用 PowerShell cmdlet Microsoft Defender 防病毒管理配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)|有关使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒的说明，以及指向所有 cmdlet 和允许的参数的文档的链接|
|[使用 Microsoft Defender 防病毒 Management Instrumentation Windows WMI (管理) ](use-wmi-microsoft-defender-antivirus.md)|有关使用 WMI 管理 Microsoft Defender 防病毒的说明，以及指向 WMIv2 API 文档的链接 (包括所有类、方法和属性) |
|[使用 Microsoft Defender 防病毒命令行MpCmdRun.exe管理命令行工具](command-line-arguments-microsoft-defender-antivirus.md)|有关使用专用命令行工具来管理和使用 Microsoft Defender 防病毒|
