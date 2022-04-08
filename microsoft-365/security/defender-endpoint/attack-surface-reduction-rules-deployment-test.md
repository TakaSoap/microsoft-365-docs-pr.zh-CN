---
title: 测试攻击面减少 (ASR) 规则
description: 提供有关测试攻击面减少 (ASR) 规则部署的指导。
keywords: 攻击面减少规则部署、ASR 部署、启用 asr 规则、配置 ASR、主机入侵防护系统、保护规则、防攻击规则、反攻击规则、攻击规则、感染预防规则、Pertahanan Microsoft untuk Titik Akhir、配置 ASR 规则
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
ms.openlocfilehash: facce2b736cb23cc41625b4b7d5c3f8b0ca5cfae
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705266"
---
# <a name="test-attack-surface-reduction-asr-rules"></a>测试攻击面减少 (ASR) 规则

测试攻击面减少 (ASR) 规则有助于确定规则是否会在启用任何规则之前阻碍业务线操作。 从受控的小型组开始，可以在跨组织扩展部署时限制潜在的工作中断。

使用环 1 开始攻击面减少 (ASR) 规则部署。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-testing-steps.png" alt-text="ASR 规则测试步骤" lightbox="images/asr-rules-testing-steps.png":::
  
## <a name="step-1-test-asr-rules-using-audit"></a>步骤 1：使用审核测试 ASR 规则

从第 1 圈中的冠军用户或设备开始，打开设置为"审核"的 ASR 规则，开始测试阶段。 通常，建议在审核) 中启用所有规则 (，以便确定在测试阶段触发的规则。 请注意，设置为"审核"的规则通常不会影响应用规则的实体或实体的功能，但确实会为评估生成记录的事件;对最终用户没有影响。

### <a name="configure-asr-rules-using-mem"></a>使用 MEM 配置 ASR 规则

可以使用 Microsoft Endpoint Manager (MEM) Endpoint Security 配置自定义 ASR 规则。

1. 打开[Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com/#home)。
2. 转到 **Endpoint SecurityAttack** >  **表面缩减**。
3. 选择“创建策略”。
4. 在 **平台** 中，选择 **Windows 10及更高版本**，并在 **"配置文件**"中选择 **"攻击面减少"规则**。
  
    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-create-profile.png" alt-text="ASR 规则的配置文件创建页" lightbox="images/asr-mem-create-profile.png":::

5. 单击“**创建**”。
6. 在 **"创建配置文件"** 窗格的"**基本** 信息"选项卡中，在 **"名称"** 中添加策略的名称。 在 **"说明** "中，添加 ASR 规则策略的说明。
7. 在" **配置设置"** 选项卡的" **攻击面减少规则**"下，将所有规则设置为 **审核模式**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-configuration-settings.png" alt-text="ASR 规则到审核模式的配置" lightbox="images/asr-mem-configuration-settings.png":::

    >[!Note]
    >某些 ASR 规则模式列表存在差异; _阻止_ 和 _启用_ 提供相同的功能。

8. [可选]在" **作用域标记"** 窗格中，可以将标记信息添加到特定设备。 还可以使用基于角色的访问控制和范围标记，确保正确的管理员有权访问和查看正确的Intune对象。 了解详细信息：[使用基于角色的访问控制 (RBAC) 以及Intune中分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。
9. 在 **"分配** "窗格中，可以将配置文件部署或"分配"到用户或设备组。 了解详细信息：[在Microsoft Intune中分配设备配置文件](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. 在 **"审阅 + 创建** "窗格中查看设置。 单击 **"创建** "以应用规则。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-review-create.png" alt-text="&quot;创建配置文件&quot;页" lightbox="images/asr-mem-review-create.png":::

ASR 规则的新攻击面减少策略在 **Endpoint 安全|中列出攻击面减少**。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-my-asr-rules.png" alt-text=" &quot;攻击面减少&quot;页" lightbox="images/asr-mem-my-asr-rules.png":::

## <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>步骤 2：了解Microsoft 365 Defender门户中的攻击面减少规则报告页

ASR 规则报告页位于 **Microsoft 365 Defender** portalReportsAttack  >  > **surface reduction rules** 中。 此页有三个选项卡：

- Detections
- 配置
- 添加排除项

### <a name="detections-tab"></a>"检测"选项卡

提供检测到的审核和阻止事件的 30 天时间线。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01.png" alt-text="&quot;攻击面减少规则检测&quot;选项卡" lightbox="images/asr-defender365-01.png":::

攻击面减少规则窗格按规则提供检测到的事件的概述。

>[!Note]
>ASR 规则报表存在一些差异。 Microsoft 正在更新 ASR 规则报表的行为，以提供一致的体验。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01b.png" alt-text="&quot;攻击面减少规则&quot;页" lightbox="images/asr-defender365-01b.png"::: 

单击 **"查看检测** "以打开" **检测"** 选项卡。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻击面减少规则检测" lightbox="images/asr-defender365-reports-detections.png":::

**GroupBy** 和 **筛选器** 窗格提供以下选项：

**GroupBy** 返回设置为以下组的结果：

- 无分组
- 检测到的文件
- 审核或阻止
- Rule
- 源应用
- Device
- User
- Publisher

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻击面减少规则检测 GroupBy 筛选器" lightbox="images/asr-defender365-reports-detections.png":::

**筛选器** 将打开 **"规则上的筛选器** "页，使你能够将结果范围限定为仅选定的 ASR 规则：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-filter.png" alt-text="攻击面减少规则检测筛选规则" lightbox="images/asr-defender365-filter.png":::

>[!Note]
>如果你有 Microsoft Microsoft 365安全 E5 或 A5，Windows E5 或 A5 许可证，则以下链接将打开 Microsoft Defender 365 报告>[攻击面减少](https://security.microsoft.com/asr?viewid=detections)>检测"选项卡。

### <a name="configuration-tab"></a>"配置"选项卡

按计算机列出 ASR 规则的聚合状态：Off、Audit、Block。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.png" alt-text="&quot;攻击面减少规则配置&quot;选项卡及其页面中的条目" lightbox="images/asr-defender365-configurations.png":::

在"配置"选项卡上，可以通过选择要查看 ASR 规则的设备来检查（按设备）启用了哪些 ASR 规则，以及在哪种模式下启用了 ASR 规则。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.settings.png" alt-text="已启用攻击面减少规则和模式" lightbox="images/asr-defender365-configurations.settings.png":::

**开始** 链接将打开Microsoft Endpoint Manager管理中心，可在其中创建或修改 ASR 的终结点保护策略：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem1.png" alt-text="&quot;概述&quot;页上的*Endpoint 安全菜单项" lightbox="images/asr-defender365-05b-mem1.png":::

在终结点安全|概述，选择 **"攻击面减少**"：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem2.png" alt-text="MEM 的攻击面减少" lightbox="images/asr-defender365-05b-mem2.png":::

终结点安全|"攻击面减少"窗格随即打开：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem3.png" alt-text="&quot;终结点安全攻击面减少&quot;窗格" lightbox="images/asr-defender365-05b-mem3.png":::

>[!Note]
>如果拥有 Microsoft Defender 365 E5 (或Windows E5？) 许可证，则此链接将打开 Microsoft Defender 365 报表>攻击面减少>[配置](https://security.microsoft.com/asr?viewid=configuration)选项卡。

### <a name="add-exclusions"></a>添加排除项

此选项卡提供一种方法来选择检测到的实体 (例如，误报) 排除。 添加排除项时，报表将提供预期影响的摘要。

>[!Note]
> MICROSOFT DEFENDER 防病毒 AV 排除项受 ASR 规则的遵守。  请参阅 [根据扩展名、名称或位置配置和验证排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)项。

> [!div class="mx-imgBorder"]
> :::image type="content" source="Images/asr-defender365-06d.png" alt-text="用于排除检测到的文件的窗格" lightbox="Images/asr-defender365-06d.png":::

> [!Note]
>如果拥有 Microsoft Defender 365 E5 (或Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面减少>[排除选项](https://security.microsoft.com/asr?viewid=exclusions)卡。

### <a name="use-powershell-as-an-alternative-method-to-enable-asr-rules"></a>使用 PowerShell 作为启用 ASR 规则的替代方法

可以使用 PowerShell（作为 MEM 的替代方法）在审核模式下启用 ASR 规则，以查看在功能完全启用时会被阻止的应用的记录。 还可以了解规则在正常使用期间触发的频率。

若要在审核模式下启用攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

[攻击面减少规则的 GUID 值](attack-surface-reduction-rules-reference.md)在哪里`<rule ID>`。

若要在审核模式下启用所有添加的攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 如果要完全审核组织中攻击面减少规则的工作原理，则需要使用管理工具将此设置部署到网络 () 中的设备。

还可以使用 组策略、Intune 或移动设备管理 (MDM) 配置服务提供商 (CSP) 来配置和部署设置。 有关主要 [攻击面减少规则](attack-surface-reduction.md) 文章的详细信息。

## <a name="use-windows-event-viewer-review-as-an-alternative-to-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>使用Windows 事件查看器审阅作为Microsoft 365 Defender门户中攻击面减少规则报告页的替代方法

若要查看已阻止的应用，请在 Microsoft-Windows-Windows Defender/操作日志中打开事件查看器并筛选事件 ID 1121。 下表列出了所有网络保护事件。

事件 ID | 描述
-|-
 5007 | 更改设置时的事件
 1121 | 攻击面减少规则在块模式下触发时发生的事件
 1122 | 在审核模式下触发攻击面减少规则时发生的事件

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[攻击面减少 (ASR) 规则部署概述](attack-surface-reduction-rules-deployment.md)

[计划攻击面减少 (ASR) 规则部署](attack-surface-reduction-rules-deployment-plan.md)

[启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)

[操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md)

[ASR) 规则引用 (攻击面减少](attack-surface-reduction-rules-reference.md)
