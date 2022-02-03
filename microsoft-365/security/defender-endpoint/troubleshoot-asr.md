---
title: 解决攻击面减少规则的问题
description: 用于解决 Microsoft Defender for Endpoint 中攻击面减少规则的问题的资源和示例代码。
keywords: 疑难解答， 错误， 修复， windows defender eg， asr， 规则， hips， 疑难解答， 审核， 排除， 误报， 损坏， 阻止， Microsoft Defender for Endpoint
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: f03fa0ac8f44acb3ce73076be4d43d913e32f969
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62326707"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>攻击面减少规则疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

当你使用 [攻击面减少规则时](attack-surface-reduction.md) ，你可能会遇到问题，例如：

- 规则阻止文件、进程或执行其他一些不应 (误报) 
- 规则不能如所述工作，或不会阻止文件或进程，它应 (漏报) 

解决这些问题有四个步骤：

1. [确认先决条件](#confirm-prerequisites)
2. [使用审核模式测试规则](#use-audit-mode-to-test-the-rule)
3. [为指定规则添加排除 (](#add-exclusions-for-a-false-positive) 用于误报) 
4. [提交支持日志](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>确认先决条件

攻击面减少规则仅适用于具有以下条件的设备：

- 终结点运行Windows 10 企业版版本 1709 (也称为 Fall Creators Update) 。

- 终结点将 Microsoft Defender 防病毒用作唯一的防病毒保护应用。 [使用任何其他防病毒应用将导致Microsoft Defender 防病毒禁用自身](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

- [实时保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 已启用。

- 审核模式未启用。 使用组策略将规则设置为已禁用 (值：**0**) 启用 [攻击面减少规则中所述](enable-attack-surface-reduction.md)。

如果满足所有先决条件，请继续执行下一步以在审核模式下测试规则。

## <a name="use-audit-mode-to-test-the-rule"></a>使用审核模式测试规则

你可以访问 [demo.wd.microsoft.com 上的 Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 测试场网站，以确认攻击面减少规则通常适用于设备上预配置的方案和进程，或者可以使用审核模式，该模式仅启用报告规则。

按照使用演示 [工具中的以下说明查看攻击面](evaluate-attack-surface-reduction.md) 减少规则如何工作，以测试遇到问题的特定规则。

1. 为要测试的特定规则启用审核模式。 使用组策略将规则设置为审核模式 (值：**2**) 启用 [攻击面减少规则中所述](enable-attack-surface-reduction.md)。 审核模式允许规则报告文件或进程，但仍允许它运行。

2. 执行导致问题的活动 (例如，打开或执行应阻止但允许其访问) 。

3. [查看攻击面减少规则事件](attack-surface-reduction.md)日志，以查看如果规则已设置为"已启用"，该规则是否阻止了文件或 **进程。**

如果某个规则未阻止预期应阻止的文件或进程，则首先检查审核模式是否已启用。

审核模式可能已启用以测试其他功能，或者由自动 PowerShell 脚本启用，并且可能在测试完成后未禁用。

如果你已使用演示工具和审核模式测试了规则，并且攻击面减少规则正在预配置的方案中运行，但规则未按预期工作，请根据你的情况继续执行以下任一部分：

1. 如果攻击面减少规则阻止了不应阻止的攻击 (也称为误报) ，你可以首先添加攻击面减少 [规则排除](#add-exclusions-for-a-false-positive)。

2. 如果攻击面减少规则未阻止它应阻止 (也称为漏报) ，你可以立即继续执行最后一步，收集诊断数据，将问题提交给 [我们](#collect-diagnostic-data-for-file-submissions)。

## <a name="add-exclusions-for-a-false-positive"></a>添加误报的排除项

如果攻击面减少规则阻止不应阻止的内容 (也称为误报) ，你可以添加排除项以防止攻击面减少规则评估排除的文件或文件夹。

若要添加排除项，请参阅 [自定义攻击面减少](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)。

> [!IMPORTANT]
> 可以指定要排除的单个文件和文件夹，但不能指定单个规则。
> 这意味着排除的任何文件或文件夹都将从所有 ASR 规则中排除。

## <a name="report-a-false-positive-or-false-negative"></a>报告误报或漏报

使用Windows Defender[基于 Web](https://www.microsoft.com/wdsi/filesubmission) 的安全智能提交表单报告网络保护的漏报或误报。 使用 Windows E5 订阅，还可以[提供指向任何关联警报的链接](alerts-queue.md)。

## <a name="collect-diagnostic-data-for-file-submissions"></a>收集文件提交的诊断数据

当你报告攻击面减少规则问题时，会要求你收集和提交诊断数据，Microsoft 支持和工程团队可以使用这些数据来帮助解决问题。

1. 打开提升的命令提示符并更改为Windows Defender目录：

   ```console
   cd "c:\program files\windows defender"
   ```

2. 运行此命令以生成诊断日志：

   ```console
   mpcmdrun -getfiles
   ```

3. 默认情况下，它们保存到 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`。 将文件附加到提交表单。

## <a name="related-articles"></a>相关文章

- [攻击面减少规则](attack-surface-reduction.md)
- [启用攻击面减少规则](enable-attack-surface-reduction.md)
- [评估攻击面减少规则](evaluate-attack-surface-reduction.md)
