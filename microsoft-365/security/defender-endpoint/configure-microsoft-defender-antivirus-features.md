---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略和 PowerShell 配置这些功能。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 配置， 配置， 配置管理器， Microsoft Endpoint Configuration Manager， SCCM， Intune， MDM， 移动设备管理， GP， 组策略， PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275104"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>配置 Microsoft Defender 防病毒软件功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用多种Microsoft Defender 防病毒配置配置策略，包括：

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- 组策略
- PowerShell cmdlet
- Windows Management Instrumentation (WMI)

可以配置以下各种功能：

- 云端保护
- 始终提供实时保护，包括行为、启发式和基于机器学习的保护
- 最终用户如何与各个终结点上的客户端交互

以下文章介绍如何在配置任务时执行Microsoft Defender 防病毒。 每篇文章都介绍了适用的配置工具 (或) 。

|文章  |说明  |
|---------|---------|
|[利用 Microsoft 云提供的Microsoft Defender 防病毒保护](cloud-protection-microsoft-defender-antivirus.md)     | 使用云提供的保护进行快速可靠的高级防病毒检测。        |
|[配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)     |启用基于行为的启发式实时防病毒保护。         |
|[配置最终用户与最终用户的Microsoft Defender 防病毒](configure-end-user-interaction-microsoft-defender-antivirus.md) | 配置组织中最终用户与用户交互的方式Microsoft Defender 防病毒他们看到的通知，以及他们是否可以覆盖设置。 |

> [!TIP]
> 还可以查看管理和配置 [工具参考](configuration-management-reference-microsoft-defender-antivirus.md) 主题，了解每个工具的概述以及进一步帮助的链接。