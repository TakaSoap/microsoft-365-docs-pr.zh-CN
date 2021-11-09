---
title: 测试 Microsoft Defender for Endpoint 功能在审核模式下如何工作
description: 审核模式可帮助你查看 Microsoft Defender for Endpoint 在启用后如何保护你的设备。
keywords: 攻击防护， 审核， 审核， 模式， 已启用， 禁用， 测试， 演示， 评估， 实验室
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 10/14/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: fd5966380b23b13ab43b3e0e0c6583db03971541
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882929"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中测试攻击面减少

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

作为组织安全团队的一部分，你可以配置攻击面减少功能以在审核模式下运行，以查看这些功能如何工作。 在审核模式下，可以启用：

- 攻击面减少规则
- 漏洞保护
- 网络保护
- 在审核模式下受控文件夹访问权限

通过审核模式，你可以查看启用该功能后将发生的情况记录。

可以在测试这些功能的运行方式时启用审核模式。 这将帮助确保你的业务线应用不受影响。 还可以了解在一定时段内发生的可疑文件修改尝试次数。

这些功能不会阻止或阻止应用、脚本或文件被修改。 但是，Windows事件日志将记录事件，就像功能完全启用一样。 使用审核模式，你可以查看事件日志，以查看如果启用该功能，将有什么影响。

若要查找审核的条目，请转到应用程序和服务 \> **Microsoft** \> **Windows Windows Defender** \>  \> **操作**。

使用 Defender for Endpoint 获取每个事件的更多详细信息，尤其是调查攻击面减少规则。 使用 Defender for Endpoint 控制台，你可以调查作为警报时间线和调查方案的 [一部分的问题](investigate-alerts.md)。

可以使用组策略、PowerShell 和配置服务提供程序和 CSP (启用审核) 。

> [!TIP]
> 还可以访问 Testground Windows Defender[网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)确认这些功能是否正常工作并查看它们如何工作。

|审核选项|如何启用审核模式|如何查看事件|
|---|---|---|
|审核适用于所有事件|[启用受控文件夹访问](enable-controlled-folders.md)|[受控文件夹访问事件](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
|审核适用于单个规则|[启用攻击面减少规则](enable-attack-surface-reduction.md)|[攻击面减少规则事件](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
|审核适用于所有事件|[启用网络保护](enable-network-protection.md)|[网络保护事件](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
|审核适用于单个缓解|[启用漏洞保护](enable-exploit-protection.md)|[Exploit Protection 事件](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
