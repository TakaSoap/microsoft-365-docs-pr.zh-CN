---
title: 部署和启用 Microsoft Defender 防病毒软件
description: 使用 Microsoft Defender 防病毒、Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 或 WMI 部署 Microsoft Intune，以保护终结点。
keywords: 部署、启用、Microsoft Defender 防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 9baa4fe5318bf21d73b3c79e719895fb9c492ea7
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164114"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a>部署和启用 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

根据你使用的管理工具，你可能需要专门启用或配置Microsoft Defender 防病毒保护。 

有关如何通过 Microsoft Intune、Microsoft Endpoint Configuration Manager、组策略、Active Directory 和 Microsoft Azure 启用保护的说明，请参阅 Microsoft Defender 防病毒 上的表。 [](deploy-manage-report-microsoft-defender-antivirus.md#ref2)、PowerShell cmdlet 和 Windows Management Instruction (WMI) 。

某些方案需要有关如何成功部署或配置 Microsoft Defender 防病毒 保护的更多指南，例如虚拟桌面基础结构 (VDI) 环境。

本节中的其余文章提供有关在 VDI 或远程桌面服务[ (RDS) ](deployment-vdi-microsoft-defender-antivirus.md)环境中在虚拟机 (VM) 上设置 Microsoft Defender 防病毒 的端到端建议和最佳做法。

## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署、管理更新并报告Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南](deployment-vdi-microsoft-defender-antivirus.md)