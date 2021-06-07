---
title: 配置攻击面减少功能
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和组策略配置攻击面减少。
keywords: asr， 攻击面减少， windows defender， microsoft defender， 防病毒， av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770957"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>配置攻击面减少功能

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。

Defender for Endpoint 包括多种攻击面减少功能。 若要了解更多信息，请参阅 [攻击面减少功能概述](overview-attack-surface-reduction.md)。 若要在你的环境中配置攻击面减少，请按照以下步骤操作： 

1. [为 Microsoft Edge 启用基于硬件的隔离](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。

2. 启用应用程序控制。 

   1. 查看 Windows 中的基本策略。 请参阅 [示例基本策略](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. 请参阅 [应用程序控件设计指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. 请参阅应用程序 [控件设计指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [启用受控文件夹访问权限](enable-controlled-folders.md)。

4. [打开网络保护](enable-network-protection.md)。

5. [启用 Exploit Protection](enable-exploit-protection.md)。

6. [配置攻击面减少规则](enable-attack-surface-reduction.md)。

7. 设置网络防火墙。

   1. 获取高级Windows Defender 防火墙[的概述](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
   2. 使用[Windows Defender 防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)设计指南决定您希望如何设计防火墙策略。
   3. 使用[Windows Defender 防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)部署指南设置组织的高级安全防火墙。 

> [!TIP]
> 在大多数情况下，配置攻击面减少功能时，可以从以下几种方法中选择：
> - Microsoft Endpoint Manager (现在包括Microsoft Intune和Microsoft Endpoint Configuration Manager) 
> - 组策略
> - PowerShell cmdlet
