---
title: 网络保护问题疑难解答
description: 用于解决 Microsoft Defender for Endpoint 中的网络保护问题的资源和示例代码。
keywords: 疑难解答， 错误， 修复， windows defender eg， asr， 规则， hips， 疑难解答， 审核， 排除， 误报， 损坏， 阻止， Microsoft Defender for Endpoint
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 131021236f5294f10f9abdf6e4ba170e2349b707
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555748"
---
# <a name="troubleshoot-network-protection"></a>网络保护疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

本文提供了网络保护的疑难解答 [信息](network-protection.md)，例如：

- 网络保护阻止安全网站 (误报) 
- 网络保护无法阻止可疑或已知的恶意网站 (漏报) 

解决这些问题有四个步骤：

1. 确认先决条件
2. 使用审核模式测试规则
3. 为指定规则添加排除 (用于误报) 
4. 提交支持日志

## <a name="confirm-prerequisites"></a>确认先决条件

网络保护仅适用于具有以下条件的设备：

> [!div class="checklist"]
>
> - 终结点运行Windows 10 专业版或Enterprise版本 1709 或更高版本。
> - 终结点将 Microsoft Defender 防病毒用作唯一的防病毒保护应用。 [查看在使用非 Microsoft 防病毒解决方案时会发生什么情况](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
> - [实时保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 已启用。
> - [云提供的保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 已启用。
> - 审核模式未启用。 使用 [组策略](enable-network-protection.md#group-policy) 将规则设置为"已禁用 **(** 值 **：0**) 。

## <a name="use-audit-mode"></a>使用审核模式

可以在审核模式下启用网络保护，然后访问我们创建的演示该功能的网站。 网络保护将允许所有网站连接，但会记录一个事件，以指示启用网络保护后可能阻止的任何连接。

1. 将网络保护设置为 **审核模式**。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 执行导致问题的连接活动 (例如，尝试访问站点，或者连接到您或不希望阻止访问的 IP) 。

3. [查看网络保护事件](network-protection.md#review-network-protection-events-in-windows-event-viewer) 日志，以查看如果该功能已设置为"已启用"，该功能是否阻止 **了连接**。

   如果网络保护未阻止预期应该阻止的连接，请启用该功能。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>报告误报或漏报

如果已使用演示网站和审核模式测试了功能，并且网络保护适用于预配置的方案，但无法按预期为特定连接工作，请使用[基于 Windows Defender](https://www.microsoft.com/wdsi/filesubmission)安全智能 Web 的提交表单报告网络保护的漏报或误报。 使用 E5 订阅，还可以 [提供指向任何关联警报的链接](alerts-queue.md)。

请参阅在 Microsoft Defender for Endpoint 中解决 [误报/负数](defender-endpoint-false-positives-negatives.md)。

## <a name="add-exclusions"></a>添加排除项
当前排除选项包括：

1.  设置自定义允许指示器。
2.  使用 IP 排除项： `Add-MpPreference -Exclusion IpAddress 192.168.1.1`
3.  排除整个过程。 有关详细信息，请参阅Microsoft Defender 防病毒[排除项](configure-exclusions-microsoft-defender-antivirus.md)。 


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

3. 将文件附加到提交表单。 默认情况下，诊断日志保存在 中 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>解决 E5 客户 (网络保护服务的连接) 

由于网络保护运行的环境，Microsoft 无法查看操作系统代理设置。 在某些情况下，网络保护客户端无法访问云服务。 要解决网络保护的连接问题，请配置以下注册表项之一，以便网络保护能够识别代理配置：

```powershell
Set-MpPreference -ProxyServer <proxy IP address: Port>
```

---OR---

```powershell
Set-MpPreference -ProxyPacUrl <Proxy PAC url>
```

可以使用 PowerShell、Microsoft Endpoint Manager或组策略配置注册表项。 以下是一些可帮助的资源：

- [使用注册表项](/powershell/scripting/samples/working-with-registry-keys)
- [配置终结点保护的自定义客户端设置](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [使用组策略设置来管理Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>另请参阅

- [网络保护](network-protection.md)
- [网络保护和 TCP 三向握手](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [网络保护功能评估](evaluate-network-protection.md)
- [启用网络保护](enable-network-protection.md)
- [在 Defender for Endpoint 中解决误报/负数](defender-endpoint-false-positives-negatives.md)
