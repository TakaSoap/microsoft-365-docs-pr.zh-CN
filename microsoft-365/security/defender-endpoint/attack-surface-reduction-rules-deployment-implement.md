---
title: 实施攻击面减少 (ASR) 规则部署
description: 提供实现攻击面减少规则部署的指导。
keywords: 攻击面减少规则部署、ASR 部署、启用 asr 规则、配置 ASR、主机入侵防护系统、保护规则、防攻击规则、反攻击规则、攻击规则、感染预防规则、Microsoft Defender for Endpoint、配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 675d881c3737b67cfdc0207be85285f71455d65c
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666957"
---
# <a name="step-3-implement-asr-rules"></a>步骤 3：实现 ASR 规则

实施攻击面减少 (ASR) 规则将第一个测试圈移动到已启用的功能状态。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-implementation-steps.png" alt-text="实现 ASR 规则的过程" lightbox="images/asr-rules-implementation-steps.png":::
  

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>步骤 1：将 ASR 规则从审核转换为阻止

1. 在审核模式下确定所有排除项后，开始将某些 ASR 规则设置为"阻止"模式，从触发事件最少的规则开始。 请参阅" [启用攻击面减少规则](enable-attack-surface-reduction.md)"。
2. 查看Microsoft 365 Defender门户中的报告页;请[参阅Microsoft Defender for Endpoint中的威胁防护报告](threat-protection-reports.md)。 另请查看 ASR 支持者的反馈。
3. 根据需要优化排除项或创建新的排除项。
4. 将有问题的规则切换回审核。

  >[!Note]
  >对于 (产生过多噪音) 规则的有问题的规则，创建排除项比关闭规则或切换回审核要好。 你必须确定什么最适合你的环境。

  >[!Tip]
  >如果可用，请利用规则中的警告模式设置来限制中断。 在"警告"模式下启用 ASR 规则可捕获触发的事件并查看其潜在中断，而无需实际阻止最终用户访问。 了解详细信息： [用户的警告模式](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告模式的工作原理是什么？

警告模式实际上是阻止指令，但用户可以选择"取消阻止"给定流或应用的后续执行。 每个设备、用户、文件和进程组合上的警告模式取消阻止。 警告模式信息存储在本地，持续时间为 24 小时。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>步骤 2：将部署扩展到 ring n + 1

如果确信已正确配置第 1 圈的 ASR 规则，则可以将部署范围扩展到下一环 (环 n + 1) 。

部署过程（步骤 1 – 3）对于每个后续环基本上相同：

1. 审核中的测试规则
2. 在Microsoft 365 Defender门户中查看 ASR 触发的审核事件
3. 创建排除项
4. 查看：根据需要优化、添加或删除排除项
5. 将规则设置为"阻止"
6. 查看Microsoft 365 Defender门户中的报表页。
7. 创建排除项。
8. 禁用有问题的规则或将其切换回审核。

#### <a name="customize-attack-surface-reduction-rules"></a>自定义减少攻击面规则

在继续扩展攻击面减少规则部署时，你可能会发现自定义已启用的攻击面减少规则是必要或有益的。

##### <a name="exclude-files-and-folders"></a>排除文件和文件夹

可以选择排除攻击面减少规则评估的文件和文件夹。 排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止该文件运行。

例如，考虑勒索软件规则：

勒索软件规则旨在帮助企业客户降低勒索软件攻击的风险，同时确保业务连续性。 默认情况下，勒索软件规则错误处于谨慎状态，并防范尚未获得足够信誉和信任的文件。 若要重新强调，勒索软件规则仅根据数百万客户的使用指标触发未获得足够积极信誉和流行率的文件。 通常，块是自行解析的，因为每个文件的"信誉和信任"值会随着非问题使用量的增加而递增升级。

如果阻止未及时自行解析，客户可以根据 _自己的风险_ 使用自助服务机制或妥协指标 (IOC) 的"允许列表"功能来取消阻止文件本身。

> [!WARNING]
> 排除或取消阻止文件或文件夹可能会允许不安全的文件运行和感染设备。 排除文件或文件夹可以严重削弱攻击面减少规则提供的保护。 会被规则阻止的文件将被允许运行，并且不会记录任何报告或事件。

排除应用于允许排除的所有规则。 可以为资源指定单个文件、文件夹路径或完全限定的域名。 但是，不能将排除项限制为特定规则。

仅当已排除的应用程序或服务启动时才应用排除项。 例如，如果为已运行的更新服务添加排除项，更新服务将继续触发事件，直到服务停止并重新启动。

攻击面减少支持环境变量和通配符。 有关使用通配符的信息，请参阅 [文件名和文件夹路径或扩展排除列表中的通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。
如果遇到检测不应检测到的文件的规则问题，请 [使用审核模式来测试规则](evaluate-attack-surface-reduction.md)。

有关每个规则的详细信息，请参阅 [攻击面减少规则参考](attack-surface-reduction-rules-reference.md) 主题。

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>使用组策略排除文件和文件夹

1. 在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在 **组策略管理编辑器** 中，转到 **"计算机配置**"，然后单击 **"管理"模板**。

3. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒Microsoft Defender 攻击防护** \>  \> **攻击面减少**。

4. 双击 **"攻击面减少规则"设置中的"排除文件和路径** "，并将选项设置为 **"已启用**"。 选择 **"显示"** ，然后在 **"值名称** "列中输入每个文件或文件夹。 在每个项的 **"值**"列中输入 **0**。

> [!WARNING]
> 请勿使用引号，因为值 **名称** 列或 **值** 列不支持引号。

##### <a name="use-powershell-to-exclude-files-and-folders"></a>使用 PowerShell 排除文件和文件夹

1. 在"开始"菜单中键入 **powershell**，右键单击 **Windows PowerShell**，然后选择 **"以管理员身份运行**"。

2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    继续使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 以向列表添加更多文件夹。

    > [!IMPORTANT]
    > 用于 `Add-MpPreference` 将应用追加或添加到列表。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>使用 MDM CSP 排除文件和文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

##### <a name="customize-the-notification"></a>自定义通知

可以自定义触发规则时的通知并阻止应用或文件。 请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[ASR 规则部署先决条件](attack-surface-reduction-rules-deployment.md)

[步骤 1：规划 ASR 规则部署](attack-surface-reduction-rules-deployment-plan.md)

[步骤 2：测试 ASR 规则](attack-surface-reduction-rules-deployment-test.md)

[步骤 4：操作 ASR 规则](attack-surface-reduction-rules-deployment-operationalize.md)
