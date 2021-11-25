---
title: 攻击面减少规则部署阶段 2 - 测试
description: 提供测试攻击面减少规则部署的指导。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: ee6e8f1ce7f6e75b2e45e058f41403433cc707d4
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171729"
---
# <a name="attack-surface-reduction-rules-deployment-phase-2-test"></a>攻击面减少规则部署阶段 2：测试

使用圈 1 开始 ASR 规则部署。

> [!div class="mx-imgBorder"]
> ![ASR 规则测试步骤](images/asr-rules-testing-steps.png)

## <a name="step-1-test-asr-rules-using-audit"></a>步骤 1：使用审核测试 ASR 规则

首先打开 ASR 规则，将规则设置为审核，从圈 1 中的冠军用户或设备开始测试阶段。 通常，建议在审核策略中启用 (规则) 以便可以确定在测试阶段触发哪些规则。 请注意，设置为"审核"的规则通常不会影响应用该规则的一个或多个实体的功能，但会为评估生成记录的事件;对最终用户没有影响。

### <a name="configure-asr-rules-using-mem"></a>使用 MEM 配置 ASR 规则

You can use Microsoft Endpoint Manager (MEM) Endpoint Security to configure custom ASR rules.

1. 打开[Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com/#home)
2. 转到终结点 **安全**  >  **攻击面减少**。
3. 选择“创建策略”。
4. 在 **平台** 中 **，Windows 10** 和更高版本，在 **配置文件** 中选择 **攻击面减少规则**。
  
    > [!div class="mx-imgBorder"]
    > ![配置 ASR 规则配置文件](images/asr-mem-create-profile.png)

5. 单击“**创建**”。
6. 在 **"创建配置文件****"窗格的**"基本信息"选项卡的 **"名称**"中，为策略添加名称。 在 **"说明** "中，添加 ASR 规则策略的说明。
7. 在" **配置设置"** 选项卡的 **"攻击面减少规则**"下，将所有规则设置为 **审核模式**。

    > [!div class="mx-imgBorder"]
    > ![将 ASR 规则设置为审核模式](images/asr-mem-configuration-settings.png)

    >[!Note]
    >某些 ASR 规则模式列表存在变化;_阻止和__启用_ 提供相同的功能。

8. [可选]在 **范围标记窗格中** ，你可以将标记信息添加到特定设备。 您还可以使用基于角色的访问控制和范围标记，以确保适当的管理员对正确的 Intune 对象具有适当的访问权限和可见性。 了解更多：在 Intune 中为分布式 IT (RBAC) 和范围标记使用 [基于角色的访问控制](/mem/intune/fundamentals/scope-tags)。
9. 在 **"分配** "窗格中，你可以将配置文件部署或"分配给"用户或设备组。 了解更多信息：[在设备上分配Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. Review your settings in the **Review + create** pane. 单击 **"创建** "以应用规则。

   > [!div class="mx-imgBorder"]
   > ![激活 ASR 规则策略](images/asr-mem-review-create.png)

适用于 ASR 规则的新攻击面减少策略在终结点安全策略中 **|攻击面减少**。

   > [!div class="mx-imgBorder"]
   > ![列出的 ASR 规则策略](images/asr-mem-my-asr-rules.png)

## <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>步骤 2：了解安全门户中的攻击面减少规则Microsoft 365 Defender页面

ASR 规则报告页面位于 **报告攻击Microsoft 365 Defender**  >    >  **报告攻击面减少规则中**。 此页面包含三个选项卡：

- Detections
- 配置
- 添加排除项

### <a name="detections-tab"></a>"检测"选项卡

提供检测到的审核和阻止事件的 30 天时间线。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则检测选项卡](images/asr-defender365-01.png)

攻击面减少规则窗格基于每个规则提供检测到的事件的概述。

>[!Note]
>ASR 规则报告中有一些变化。 Microsoft 正在更新 ASR 规则报告的行为以提供一致的体验。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则规则检测](images/asr-defender365-01b.png)

单击 **"查看检测** "以打开 **"检测"** 选项卡。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则检测](images/asr-defender365-reports-detections.png)

**"GroupBy"** 和"**筛选器**"窗格提供以下选项：

**GroupBy** 返回结果集到以下组：

- 无分组
- 检测到的文件
- 审核或阻止
- Rule
- 源应用
- Device
- User
- Publisher

> [!div class="mx-imgBorder"]
> ![攻击面减少规则检测 GroupBy 筛选器](images/asr-defender365-reports-detections.png)

**筛选器** 将 **打开"筛选规则** "页，利用该页，您可以仅将结果范围确定为所选的 ASR 规则：

> [!div class="mx-imgBorder"]
> ![攻击面减少规则检测筛选规则](images/asr-defender365-filter.png)

>[!Note]
>如果你有 Microsoft Microsoft 365 安全 E5 或 A5、Windows E5 或 A5 许可证，则以下链接将打开 Microsoft Defender 365 报告 >[攻击](https://security.microsoft.com/asr?viewid=detections)面>检测"选项卡。

### <a name="configuration-tab"></a>"配置"选项卡

基于每台计算机列出 – ASR 规则的聚合状态：关闭、审核、阻止。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则配置选项卡](images/asr-defender365-configurations.png)

在"配置"选项卡上，可以通过选择要查看其 ASR 规则的设备来检查（基于每个设备）启用哪些 ASR 规则以及在哪个模式下。

> [!div class="mx-imgBorder"]
> ![攻击面减少规则已启用和模式](images/asr-defender365-configurations.settings.png)

"**入门"** 链接Microsoft Endpoint Manager管理中心，可在其中为 ASR 创建或修改终结点保护策略：

> [!div class="mx-imgBorder"]
> ![MEM 中的攻击面减少规则](images/asr-defender365-05b-mem1.png)

在终结点安全|概述，选择 **攻击面减少**：

> [!div class="mx-imgBorder"]
> ![MEM 中的攻击面减少](images/asr-defender365-05b-mem2.png)

终结点安全|将打开攻击面减少窗格：

> [!div class="mx-imgBorder"]
> ![终结点安全管理窗格](images/asr-defender365-05b-mem3.png)

>[!Note]
>如果你有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面减少 >[配置](https://security.microsoft.com/asr?viewid=configuration)"选项卡。

### <a name="add-exclusions"></a>添加排除项

此选项卡提供了一种方法来选择检测到的实体 (例如，误报) 排除。 添加排除项后，报告会提供预期影响的摘要。

>[!Note]
> Microsoft Defender 防病毒 AV 排除项由 ASR 规则遵守。  请参阅 [配置并验证基于扩展名、名称或位置的排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

> [!div class="mx-imgBorder"]
> ![终结点安全 Asr 工具](Images/asr-defender365-06d.png)

> [!Note]
>如果你有 Microsoft Defender 365 E5 (或 Windows E5？) 许可证，此链接将打开 Microsoft Defender 365 报告>攻击面减少>[排除](https://security.microsoft.com/asr?viewid=exclusions)"选项卡。

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[攻击面减少规则部署指南 - 概述](attack-surface-reduction-rules-deployment.md)

[攻击面减少规则部署阶段 1 - 计划](attack-surface-reduction-rules-deployment-phase-1.md)

[攻击面减少规则部署阶段 3 - 实施](attack-surface-reduction-rules-deployment-phase-3.md)

[攻击面减少规则部署阶段 4 - 可操作](attack-surface-reduction-rules-deployment-phase-4.md)
