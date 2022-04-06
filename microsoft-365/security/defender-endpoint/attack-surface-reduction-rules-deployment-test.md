---
title: 测试攻击面减少 (ASR) 规则
description: 提供在 ASR 规则部署中 (攻击) 指南。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
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
ms.openlocfilehash: 2f3a97da3eff16a639df995d88b9ceda91497f11
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475402"
---
# <a name="step-2-test-asr-rules"></a>步骤 2：测试 ASR 规则

测试攻击面 (ASR) 规则可帮助你在启用任何规则之前确定规则是否将妨碍业务线操作。 通过从一个小型的受控组开始，可以限制在整个组织中扩展部署时的潜在工作中断。

使用圈 1 开始 (ASR) 部署攻击面减少。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-testing-steps.png" alt-text="ASR 规则测试步骤" lightbox="images/asr-rules-testing-steps.png":::
  

## <a name="step-1-test-asr-rules-using-audit"></a>步骤 1：使用审核测试 ASR 规则

首先打开 ASR 规则，将规则设置为审核，从圈 1 中的冠军用户或设备开始测试阶段。 通常，建议在审核策略中 (所有) ，以便可以确定在测试阶段触发的规则。 请注意，设置为"审核"的规则通常不会影响应用该规则的一个或多个实体的功能，但会为评估生成记录的事件;对最终用户没有影响。

### <a name="configure-asr-rules-using-mem"></a>使用 MEM 配置 ASR 规则

可以使用 MEM Microsoft Endpoint Manager (终结点) 配置自定义 ASR 规则。

1. 打开[Microsoft Endpoint Manager管理中心。](https://endpoint.microsoft.com/#home)
2. 转到终结点 **安全** > **附加图面减少**。
3. 选择“创建策略”。
4. 在 **平台** 中，**Windows 10** 和更高版本，在 **配置文件** 中选择攻击 **面减少规则**。
  
    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-create-profile.png" alt-text="ASR 规则的配置文件创建页面" lightbox="images/asr-mem-create-profile.png":::

5. 单击“**创建**”。
6. 在 **"创建配置文件****"窗格的**"基本信息"选项卡的 **"名称**"中，为策略添加名称。 在 **"说明** "中，添加 ASR 规则策略的说明。
7. 在" **配置设置"** 选项卡的" **攻击面减少** 规则"下，将所有规则设置为 **审核模式**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-configuration-settings.png" alt-text="将 ASR 规则配置到审核模式" lightbox="images/asr-mem-configuration-settings.png":::

    >[!Note]
    >某些 ASR 规则模式列表存在变化;_阻止和__启用_ 提供相同的功能。

8. [可选]在 **范围标记窗格中** ，你可以将标记信息添加到特定设备。 您还可以使用基于角色的访问控制和范围标记，以确保适当的管理员对正确的 Intune 对象具有适当的访问权限和可见性。 了解更多信息 [：在 Intune 中为分布式 IT (RBAC](/mem/intune/fundamentals/scope-tags)) 和范围标记使用基于角色的访问控制。
9. 在 **"分配** "窗格中，你可以将配置文件部署或"分配给"用户或设备组。 了解更多信息：[在设备上分配Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. Review your settings in the **Review + create** pane. 单击 **"创建** "以应用规则。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-review-create.png" alt-text="&quot;创建配置文件&quot;页" lightbox="images/asr-mem-review-create.png":::

适用于 ASR 规则的新攻击面减少策略在终结点安全策略中 **|攻击面减少**。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-my-asr-rules.png" alt-text=" 攻击面减少页面" lightbox="images/asr-mem-my-asr-rules.png":::

## <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>步骤 2：了解安全门户中的攻击面减少规则Microsoft 365 Defender页面

ASR 规则报告页位于 **Microsoft 365 Defender** **portalReportsAttack** >  >  **图面减少规则中**。 此页面包含三个选项卡：

- Detections
- 配置
- 添加排除项

### <a name="detections-tab"></a>"检测"选项卡

提供检测到的审核和阻止事件的 30 天时间线。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01.png" alt-text="攻击面减少规则检测选项卡" lightbox="images/asr-defender365-01.png":::

攻击面减少规则窗格基于每个规则提供检测到的事件的概述。

>[!Note]
>ASR 规则报告中有一些变化。 Microsoft 正在更新 ASR 规则报告的行为以提供一致的体验。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01b.png" alt-text="攻击面减少规则页" lightbox="images/asr-defender365-01b.png"::: 

单击 **"查看检测** "以打开 **"检测"** 选项卡。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻击面减少规则检测" lightbox="images/asr-defender365-reports-detections.png":::

" **GroupBy** "和" **筛选器** "窗格提供以下选项：

**GroupBy** 返回结果集到以下组：

- 无分组
- 检测到的文件
- 审核或阻止
- Rule
- 源应用
- Device
- User
- 发布者

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻击面减少规则检测 GroupBy 筛选器" lightbox="images/asr-defender365-reports-detections.png":::

**筛选器** 将 **打开"筛选规则** "页，利用该页，您可以仅将结果范围确定为所选的 ASR 规则：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-filter.png" alt-text="攻击面减少规则检测筛选规则" lightbox="images/asr-defender365-filter.png":::

>[!Note]
>如果你有 Microsoft Microsoft 365 安全 E5 或 A5、Windows E5 或 A5 许可证，以下链接将打开 Microsoft Defender 365 报告 > 攻击面入侵 > 检测"选项卡。[](https://security.microsoft.com/asr?viewid=detections)

### <a name="configuration-tab"></a>"配置"选项卡

基于每台计算机列出 ASR 规则的聚合状态：关闭、审核、阻止。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.png" alt-text="攻击面减少规则配置选项卡及其页面中的条目" lightbox="images/asr-defender365-configurations.png":::

在"配置"选项卡上，通过选择要查看其 ASR 规则的设备，可以按设备检查已启用的 ASR 规则以及启用的模式。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.settings.png" alt-text="攻击面减少规则已启用和模式" lightbox="images/asr-defender365-configurations.settings.png":::

"**入门"** 链接Microsoft Endpoint Manager管理中心，可在其中为 ASR 创建或修改终结点保护策略：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem1.png" alt-text="概述页上的 *Endpoint 安全菜单项" lightbox="images/asr-defender365-05b-mem1.png":::

在终结点安全|概述，选择 **攻击面减少**：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem2.png" alt-text="MEM 中攻击面的减少" lightbox="images/asr-defender365-05b-mem2.png":::

终结点安全|将打开攻击面减少窗格：

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem3.png" alt-text="终结点安全攻击面减少窗格" lightbox="images/asr-defender365-05b-mem3.png":::

>[!Note]
>如果你有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告 > 攻击面减少 > [配置](https://security.microsoft.com/asr?viewid=configuration)"选项卡。

### <a name="add-exclusions"></a>添加排除项

此选项卡提供了一种方法，用于选择检测到 (，例如，误报) 排除。 添加排除项后，报告会提供预期影响的摘要。

>[!Note]
> Microsoft Defender 防病毒 AV 排除项受 ASR 规则使用。  请参阅 [配置并验证基于扩展名、名称或位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

> [!div class="mx-imgBorder"]
> :::image type="content" source="Images/asr-defender365-06d.png" alt-text="用于排除检测到的文件的窗格" lightbox="Images/asr-defender365-06d.png":::

> [!Note]
>如果你有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面减少>[排除](https://security.microsoft.com/asr?viewid=exclusions)"选项卡。

### <a name="use-powershell-as-an-alternative-method-to-enable-asr-rules"></a>使用 PowerShell 作为启用 ASR 规则的替代方法

可以使用 PowerShell（作为 MEM 的替代方法）在审核模式下启用 ASR 规则，以查看在功能完全启用时可能已被阻止的应用记录。 您还可以了解规则在正常使用期间将多久发生一次。

若要在审核模式下启用攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

其中 `<rule ID>` 是 [攻击面减少规则的 GUID 值](attack-surface-reduction-rules-reference.md)。

若要在审核模式下启用所有添加的攻击面减少规则，请使用以下 PowerShell cmdlet：

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 如果你想要完全审核攻击面减少规则在组织中如何工作，你将需要使用管理工具将此设置部署到网络中设备 () 。

您还可以使用组策略、Intune 或移动设备管理 (MDM) 配置服务提供程序 (CSP) 配置和部署设置。 在主要的攻击 [面减少规则文章中了解更多信息](attack-surface-reduction.md) 。

## <a name="use-windows-event-viewer-review-as-an-alternative-to-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>使用Windows事件查看器查看作为攻击面减少规则报告页面的替代方法，在 Microsoft 365 Defender 门户

若要查看已阻止的应用，请打开事件查看器，并筛选 Microsoft-Windows-Windows Defender/Operational 日志中的事件 ID 1121。 下表列出了所有网络保护事件。

事件 ID | 描述
-|-
 5007 | 更改设置时的事件
 1121 | 攻击面减少规则在阻止模式下触发时的事件
 1122 | 在审核模式下触发攻击面减少规则时的事件

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[ASR 规则部署先决条件](attack-surface-reduction-rules-deployment.md)

[步骤 1：规划 ASR 规则部署](attack-surface-reduction-rules-deployment-plan.md)

[步骤 3：实现 ASR 规则](attack-surface-reduction-rules-deployment-implement.md)

[步骤 4：操作 ASR 规则](attack-surface-reduction-rules-deployment-operationalize.md)
