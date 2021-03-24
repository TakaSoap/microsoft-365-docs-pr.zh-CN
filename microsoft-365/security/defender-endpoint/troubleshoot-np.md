---
title: 网络保护问题疑难解答
description: 用于解决 Microsoft Defender for Endpoint 中的网络保护问题的资源和示例代码。
keywords: 疑难解答， 错误， 修复， windows defender eg， asr， 规则， hips， 疑难解答， 审核， 排除， 误报， 损坏， 阻止， microsoft defender 终结点， microsoft defender 高级威胁防护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 165c17bc820403ebfbbe5cdfe3ca856e8416c593
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055903"
---
# <a name="troubleshoot-network-protection"></a>网络保护疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


使用网络 [保护时](network-protection.md) ，可能会遇到问题，例如：

- 网络保护阻止安全网站 (误报) 
- 网络保护无法阻止可疑或已知的恶意网站 (漏报) 

解决这些问题有四个步骤：

1. 确认先决条件
2. 使用审核模式测试规则
3. 为指定的误报规则 (排除项) 
4. 提交支持日志

## <a name="confirm-prerequisites"></a>确认先决条件

网络保护仅适用于具有以下条件的设备：

>[!div class="checklist"]
> - 终结点运行的是 Windows 10 专业版或企业版版本 1709 或更高版本。
> - 终结点使用 Microsoft Defender 防病毒作为唯一的防病毒保护应用。 [查看使用非 Microsoft 防病毒解决方案时会发生什么情况](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
> - [实时保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 已启用。
> - [云提供的保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 已启用。
> - 审核模式未启用。 使用 [组策略](enable-network-protection.md#group-policy)将规则设置为禁用 (值 **：0**) 。

## <a name="use-audit-mode"></a>使用审核模式

可以在审核模式下启用网络保护，然后访问我们创建的演示该功能的网站。 网络保护将允许所有网站连接，但会记录一个事件，以指示启用网络保护后可能阻止的任何连接。

1. 将网络保护设置为 **审核模式**。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 执行导致问题的连接活动 (例如，尝试访问站点，或者连接到您这样做或不希望阻止访问的 IP) 。

3. [查看网络保护事件](network-protection.md#review-network-protection-events-in-windows-event-viewer) 日志，以查看如果该功能已设置为"已启用"，该功能是否阻止 **了连接**。
   
   如果网络保护未阻止预期应该阻止的连接，请启用该功能。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>报告误报或漏报

如果已使用演示网站和审核模式测试了该功能，并且网络保护适用于预配置的方案，但无法按预期为特定连接工作，请使用 [基于 Windows Defender](https://www.microsoft.com/wdsi/filesubmission) 安全智能 Web 的提交表单报告网络保护的漏报或误报。 使用 E5 订阅，还可以 [提供指向任何关联警报的链接](alerts-queue.md)。

请参阅在 Microsoft Defender for Endpoint 中解决 [误报/负数](defender-endpoint-false-positives-negatives.md)。

## <a name="exclude-website-from-network-protection-scope"></a>从网络保护范围排除网站

若要允许被阻止的网站 (误报) ，请将其 URL 添加到 [受信任网站列表中](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)。 此列表中的 Web 资源绕过网络保护检查。

## <a name="collect-diagnostic-data-for-file-submissions"></a>收集文件提交的诊断数据

当你报告网络保护问题时，会要求你收集和提交诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决问题。

1. 打开提升的命令提示符并更改为Windows Defender目录：

   ```console
   cd c:\program files\windows defender
   ```

2. 运行此命令以生成诊断日志：

   ```console
   mpcmdrun -getfiles
   ```

3. 默认情况下，它们保存到 C：\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab。 将文件附加到提交表单。

## <a name="related-topics"></a>相关主题

- [网络保护](network-protection.md)
- [评估网络保护](evaluate-network-protection.md)
- [启用网络保护](enable-network-protection.md)
- [在 Defender for Endpoint 中解决误报/负数](defender-endpoint-false-positives-negatives.md)
