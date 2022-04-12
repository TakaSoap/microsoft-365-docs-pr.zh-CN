---
title: 排查网络保护问题
description: 用于排查Microsoft Defender for Endpoint中网络保护问题的资源和示例代码。
keywords: 故障排除， 错误， 修复， windows defender eg， asr， 规则， 臀部， 故障排除， 审核， 排除， 误报， 损坏， 阻止， Microsoft Defender for Endpoint
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
ms.openlocfilehash: fbb3a9e038dcd9f342065d538762b41c0673f7e6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783152"
---
# <a name="troubleshoot-network-protection"></a>网络保护疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

本文提供 [有关网络保护](network-protection.md)的故障排除信息，例如：

- 网络保护会阻止安全的网站 (误报) 
- 网络保护无法阻止可疑或已知的恶意网站 (假负) 

排查这些问题有四个步骤：

1. 确认先决条件
2. 使用审核模式测试规则
3. 为误报添加指定规则 (的排除项) 
4. 提交支持日志

## <a name="confirm-prerequisites"></a>确认先决条件

网络保护仅适用于具有以下条件的设备：

> [!div class="checklist"]
>
> - 终结点运行Windows 10 专业版或Enterprise版本 1709 或更高版本。
> - 终结点使用Microsoft Defender 防病毒作为唯一的防病毒保护应用。 [查看使用非 Microsoft 防病毒解决方案时会发生什么情况](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
> - 已启用[实时保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。
> - 已启用[云传递的保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。
> - 未启用审核模式。 使用 [组策略](enable-network-protection.md#group-policy)将规则设置为 **“已禁用**” (值：**0**) 。

## <a name="use-audit-mode"></a>使用审核模式

可以在审核模式下启用网络保护，然后访问我们创建的网站来演示该功能。 网络保护将允许所有网站连接，但会记录一个事件，以指示在启用网络保护时会被阻止的任何连接。

1. 将网络保护设置为 **审核模式**。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. 执行导致问题 (的连接活动，例如，尝试访问站点或连接到你执行或不想阻止) 的 IP 地址。

3. [查看网络保护事件日志](network-protection.md#review-network-protection-events-in-windows-event-viewer) ，查看如果该功能设置为 **“已启用**”，该功能是否会阻止连接。

   如果网络保护未阻止预期应阻止的连接，请启用该功能。

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>报告误报或误报

如果已使用演示站点和审核模式测试了该功能，并且网络保护正在处理预配置方案，但未按预期运行特定连接，请使用[基于 Windows Defender 安全智能 Web 的提交表单](https://www.microsoft.com/wdsi/filesubmission)报告网络保护的误报或误报。 借助 E5 订阅，还可以提供指向 [任何关联警报的链接](alerts-queue.md)。

请参阅[Microsoft Defender for Endpoint中的地址误报/负](defender-endpoint-false-positives-negatives.md)数。

## <a name="add-exclusions"></a>添加排除项

当前排除选项包括：

1. 设置自定义允许指示器。
2. 使用 IP 排除项： `Add-MpPreference -ExclusionIpAddress 192.168.1.1`
3. 排除整个过程。 有关详细信息，请参阅[Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md)。 

## <a name="collect-diagnostic-data-for-file-submissions"></a>收集文件提交的诊断数据

报告网络保护问题时，系统会要求你收集和提交可由 Microsoft 支持和工程团队用来帮助排查问题的诊断数据。

1. 打开提升的命令提示符并更改为Windows Defender目录：

   ```console
   cd c:\program files\windows defender
   ```

2. 运行此命令以生成诊断日志：

   ```console
   mpcmdrun -getfiles
   ```

3. 将文件附加到提交表单。 默认情况下，诊断日志保存在 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`。

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>解决 E5 客户的网络保护 (的连接问题) 

由于运行网络保护的环境，Microsoft 无法看到操作系统代理设置。 在某些情况下，网络保护客户端无法访问云服务。 若要解决网络保护的连接问题，请配置以下注册表项之一，以便网络保护能够了解代理配置：

```powershell
Set-MpPreference -ProxyServer <proxy IP address: Port>
```

---OR---

```powershell
Set-MpPreference -ProxyPacUrl <Proxy PAC url>
```

可以使用 PowerShell、Microsoft Endpoint Manager 或 组策略 配置注册表项。 下面是一些帮助的资源：

- [使用注册表项](/powershell/scripting/samples/working-with-registry-keys)
- [配置终结点保护的自定义客户端设置](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [使用组策略设置管理Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>另请参阅

- [网络保护功能](network-protection.md)
- [网络保护和 TCP 三向握手](network-protection.md#network-protection-and-the-tcp-three-way-handshake)
- [网络保护功能评估](evaluate-network-protection.md)
- [启用网络保护](enable-network-protection.md)
- [在 Defender for Endpoint 中解决误报/负](defender-endpoint-false-positives-negatives.md)
