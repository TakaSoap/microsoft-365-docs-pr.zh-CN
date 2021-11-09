---
title: 评估攻击面减少规则
description: 了解攻击面减少如何使用自定义演示工具阻止和阻止攻击。
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 评估， 测试， 演示
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: e16899f831a8c7e937ea1c1600591572f8ecb445
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882113"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>评估攻击面减少规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

攻击面减少规则有助于防止恶意软件通常用来危害设备或网络的操作。 攻击面减少规则有助于关闭恶意软件和勒索软件使用的许多常见入口点。

为运行以下任一版本和版本的设备设置攻击面减少规则Windows：

- Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows服务器版本[1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
-  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) 
- Windows Server 2022

> [!WARNING]
> 在客户端上启用攻击服务Windows Server 2016可能会导致意外结果，并影响服务器性能。 建议不要启用攻击面减少规则或将攻击面减少规则部署到不受支持的平台。

了解如何通过启用审核模式直接在你的组织中测试[](audit-windows-defender.md)功能来评估攻击面减少规则。

> [!TIP]
> 还可以访问 Microsoft Defender for Endpoint 演示方案[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 以确认功能是否正常工作并查看其工作方式。

## <a name="use-audit-mode-to-measure-impact"></a>使用审核模式衡量影响

在审核模式下启用攻击面减少规则，以查看在功能完全启用时可能阻止的应用记录。 测试此功能在组织中如何工作，以确保它不会影响你的业务线应用。 您还可以了解规则在正常使用期间将多久发生一次。

若要在审核模式下启用攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

其中 `<rule ID>` 是 [攻击面减少规则的 GUID 值](attack-surface-reduction-rules.md)。

若要在审核模式下启用所有添加的攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 如果你想要完全审核攻击面减少规则在组织中如何工作，你将需要使用管理工具将此设置部署到网络中设备 () 。

您还可以使用组策略、Intune 或移动设备管理 (MDM) 配置服务提供程序 (CSP) 配置和部署设置。 在主要的攻击 [面减少规则文章中了解更多信息](attack-surface-reduction.md) 。

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>查看事件查看器中的攻击Windows减少事件

若要查看已阻止的应用，请打开事件查看器，并筛选 Microsoft-Windows-Windows Defender/Operational 日志中的事件 ID 1121。 下表列出了所有网络保护事件。

事件 ID | 描述
-|-
 5007 | 更改设置时的事件
 1121 | 攻击面减少规则在阻止模式下触发时的事件
 1122 | 在审核模式下触发攻击面减少规则时的事件

## <a name="customize-attack-surface-reduction-rules"></a>自定义减少攻击面规则

在评估过程中，你可能希望单独配置每个规则，或将某些文件和进程排除在功能评估外。

有关 [使用管理工具（](customize-attack-surface-reduction.md) 包括组策略和 MDM CSP 策略）配置功能的信息，请参阅自定义攻击面减少规则。

## <a name="see-also"></a>另请参阅

- [使用攻击面减少规则减少攻击面](attack-surface-reduction.md)
- [使用审核模式评估Windows Defender](audit-windows-defender.md)
- [关于攻击面减少的常见问题解答](attack-surface-reduction.md)
