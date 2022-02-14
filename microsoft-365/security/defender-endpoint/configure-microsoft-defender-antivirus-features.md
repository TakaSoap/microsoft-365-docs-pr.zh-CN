---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略和 PowerShell 配置 Microsoft Endpoint Configuration Manager 功能。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 配置， 配置管理器， Microsoft Endpoint Configuration Manager， SCCM， Intune， MDM， 移动设备管理， GP， 组策略， PowerShell
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/14/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 183fedefbbb56411674ff80a9feedc507cff0530
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807520"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>配置 Microsoft Defender 防病毒软件功能


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

可以使用多种Microsoft Defender 防病毒配置配置策略，例如：

- Microsoft Endpoint Manager (包括Microsoft Intune和Microsoft Endpoint Configuration Manager) 
- 组策略
- PowerShell cmdlet
- Windows Management Instrumentation (WMI)
- [租户附加](/mem/configmgr/tenant-attach/)

可以配置以下各种功能：

- 云保护。 请参阅[云提供的保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)

- 始终提供实时保护，包括行为、启发式和基于机器学习的保护。 请参阅 [配置行为、启发式和实时保护](configure-protection-features-microsoft-defender-antivirus.md)。

- 最终用户如何与各个终结点上的客户端交互。 参阅以下资源：
  - [阻止用户查看或Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [阻止或允许用户在本地修改Microsoft Defender 防病毒策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> 查看 [管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)。
