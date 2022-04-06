---
title: 试用 Microsoft Defender for Office 365，在生产环境中使用评估
description: 针对活动用户和现有用户组试点评估的步骤，以便正确测试 Microsoft Defender for Office 365。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: d8cd0132c8b02ae29cf49c9a700a868fa3a93554
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64501346"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>试用 Microsoft Defender for Office 365

**适用于：**
- Microsoft 365 Defender

本文是设置 Microsoft Defender for Office 365 评估环境过程中的第 3 步（第 [3](eval-defender-office-365-overview.md) Office 365）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-office-365-overview.md)。

使用以下步骤设置和配置 Microsoft Defender for Office 365。

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="在 Microsoft Defender for Office 365 门户中创建试点的步骤" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [步骤 1：创建试点组](#step-1-create-pilot-groups)
- [步骤 2：配置保护](#step-2-configure-protection)
- [步骤 3：试用功能 - 熟悉模拟、监视和指标](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

评估 Microsoft Defender Office 365时，你可以选择先试点特定用户，然后再为整个组织启用和实施策略。 创建通讯组可帮助管理部署过程。 例如，创建适用于 *Office 365 用户的 Defender -* 标准保护、*适用于 Office 365 用户的 Defender -* 严格保护、*Office 365 用户的 Defender -* 自定义保护或 *适用于 Office 365 用户的 Defender - 例外。*

为什么"标准"和"严格"用于这些组术语可能并不明显，但在你浏览有关 Defender for Office 365安全预设的更多内容时，这一点将变得清晰。 命名组"自定义"和"例外"代表自己，虽然大多数用户都应在标准和严格下，但自定义和例外组将收集关于管理风险的有价值的数据。

## <a name="step-1-create-pilot-groups"></a>步骤 1：创建试点组

通讯组可以直接在本地 Active Directory 中创建和Exchange Online或同步。

1. 使用已被授予Exchange管理员角色或委派组管理权限 (帐户登录到 E) AC (管理中心帐户。
2. 从导航菜单中，展开 *"收件人"，* 然后选择"组 *"*。

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" 要单击的&quot;组&quot;菜单项" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. 从组仪表板中，选择"添加组"。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="要单击的&quot;添加组&quot;选项" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. 对于组类型，选择" *分发"* ，然后单击"下一步"。

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" &quot;选择组类型&quot;部分" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. 为组指定名称和说明，然后单击"下一步"。

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="设置基础知识部分" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>步骤 2：配置保护

默认情况下，Defender for Office 365中的某些功能已配置并打开，但安全操作可能需要从默认级别提升保护级别。

某些功能 *尚未* 配置。 有三个选项用于配置保护：

- **自动分配预设安全策略** [— 预设](../office-365-security/preset-security-policies.md) 安全策略作为一种方法提供，可快速在所有功能之间分配统一级别的保护。 可以从 standard_ 或 ***_*_strict 中选择_**。 一个好方法是从预设安全策略开始，然后在你了解有关功能和你自己的独特威胁环境更多信息时微调策略。 此处的优势在于，您可以尽快保护用户组，并随后调整保护。  (建议使用此方法。) 
- **手动配置基线保护** - 如果你希望自己配置环境，可以按照防止威胁中的指导快速 [实现保护基线](../office-365-security/protect-against-threats.md)。 通过此方法，您可以了解有关可配置设置的信息。 并且，您可以稍后微调策略。
- **配置 *自定义* 保护策略** - 还可以生成和分配自定义保护策略作为评估的一部分。 在开始自定义策略之前，必须了解应用和强制执行这些保护策略的优先级。 即使应用预设，安全操作也需要创建一些策略，以便为"链接"和"附件"保险箱安全策略保险箱策略。
> [!IMPORTANT]
> **如果需要配置** 自定义保护策略，应检查此处标准安全定义和严格安全定义的值：*[EOP 和 Microsoft Defender](../office-365-security/recommended-settings-for-eop-and-office365.md)* 的推荐设置Office 365安全。 还会列出默认值，如发生任何配置之前所见。 保留自定义内部版本偏离位置的电子表格。

### <a name="assign-preset-security-policies"></a>分配预设安全策略

建议在评估 MDO 时先从推荐的基准策略开始，然后在评估期间根据需要细化这些策略。

你可以快速启用推荐的 EOP 和 Defender Office 365保护策略，并将其分配给特定试点用户或已定义的组作为评估的一部分。 预设策略提供基线 **标准** 保护模板或 **更主动的** 严格保护模板，可单独分配或组合使用。

下面是介绍[这些步骤的 EOP 和 Microsoft Defender for Office 365](../office-365-security/preset-security-policies.md)中的预设安全策略。

1. 登录到你的 Microsoft 365 租户。 使用有权访问 Microsoft 365 Defender 门户的帐户、添加到 Office 365 中的组织管理角色或 Microsoft 365。
2. From the navigation menu， select *Polices & Rules* under Email & Collaboration.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" 策略&要单击的规则菜单项" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. 在"策略&规则"仪表板上，单击" *威胁策略"*。

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" 要单击的威胁策略菜单项" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. 从Microsoft 365 Defender门户中，从导航菜单中展开"威胁管理"，然后从子菜单中选择"策略"。
5. 在"策略"仪表板上，单击 *"预设安全策略"*。

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="威胁策略的类型" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. 单击 *"编辑* "以配置和分配标准策略和/或严格策略。

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="应用于&quot;预设安全策略&quot;页上各种策略的各种设置" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. 添加条件以根据需要将基线 ***EOP** _ 保护应用于特定试点用户或用户组，然后选择"_Next*"继续。

   例如，如果收件人是 *Office 365 Standard Protection* 组定义的 Defender 的成员，然后通过向该组添加帐户或删除帐户进行管理，则可能会应用适用于试点评估的 Defender for Office 365 条件。

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="被视为 EOP 保护的策略" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. 添加条件以根据需要将基线 ***MDO** _ 保护应用于特定试点用户或用户组。 单击_Next*继续。

   例如，如果收件人是 *定义的 Office 365 Standard Protection 组 Defender* 的成员，然后通过组添加/删除帐户进行管理，则可能会应用适用于试点评估的 Defender for Office 365 条件。

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="策略视为防御Office 365保护" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. 查看并确认更改以分配预设安全策略。
10. 通过返回到 Microsoft 365 Defender 门户 > 策略 & 规则 > 威胁策略 > 并单击"预设安全策略"磁贴，可以管理预设保护策略 (重新配置、重新应用、禁用等 ) 。

### <a name="configure-custom-protection-policies"></a>配置自定义保护策略

预定义的 *Standard* 或 *Strict* Defender for Office 365模板为试点用户提供推荐的基线保护。 但是，作为评估的一部分，还可以生成和分配自定义保护策略。

必须 *了解这些* 保护策略在应用和强制执行时优先级，如电子邮件保护的顺序和优先级- [Office 365说明。](../office-365-security/how-policies-and-protections-are-combined.md)

下表提供了有关配置和分配自定义保护策略的参考和更多指南：

<br>

****

|Policy|Description|参考|
|:---:|---|---|
|连接筛选|按 IP 地址标识好或坏的源电子邮件服务器。|[在 EOP 中配置默认连接筛选器策略](../office-365-security/configure-the-connection-filter-policy.md)|
|反恶意软件|保护用户免受电子邮件恶意软件的攻击，包括要采取的操作以及检测到恶意软件时要通知的用户。|[在 EOP 中配置反恶意软件策略](../office-365-security/configure-anti-malware-policies.md)|
|反欺骗|使用欺骗智能和欺骗智能见解保护用户免受欺骗尝试。|[在 Defender for Office 365](../office-365-security/learn-about-spoof-intelligence.md)|
|反垃圾邮件|防止用户收到垃圾电子邮件，包括检测到垃圾邮件时要采取的操作。|[在 Defender for Office 365](../office-365-security/configure-your-spam-filter-policies.md)|
|防钓鱼|保护用户免受网络钓鱼攻击，并配置可疑邮件的安全提示|[在 Defender for Office 365 中配置反钓鱼策略](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|安全附件|保护用户免受电子邮件附件中的恶意内容以及电子邮件SharePoint、OneDrive和Teams。|[在 Defender for Office 365](../office-365-security/set-up-safe-attachments-policies.md)|
|安全链接|防止用户在电子邮件或桌面应用中打开和共享Office链接。|[在 Defender for Office 365](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>步骤 3：试用功能并熟悉模拟、监视和指标

现在，你的试点已设置和配置，熟悉 Microsoft Defender for Microsoft 365 独有的报告、监视和攻击模拟工具Microsoft 365。

<br>

****

|功能|说明|更多信息|
|---|---|---|
|威胁资源管理器|威胁资源管理器是一款功能强大的近实时工具，可帮助安全运营团队调查和响应威胁，并显示有关 Office 365 中电子邮件和文件中可疑恶意软件和网络钓鱼的信息，以及组织面临的其他安全威胁和风险。|[威胁资源管理器和实时检测中的视图](../office-365-security/threat-explorer-views.md)|
|攻击模拟器|可以使用攻击门户中的攻击模拟Microsoft 365 Defender在组织中运行实际的攻击方案，这可以帮助你在真实攻击影响你的环境之前识别并查找易受攻击的用户。|[开始使用攻击模拟培训](../office-365-security/attack-simulation-training-get-started.md)|
|报表仪表板|在左侧导航菜单上，单击"报告"，然后展开"电子邮件&协作"标题。 Email & collaboration reports are about spoofing security trends some of which will allow you to take action (through buttons like 'Go to submissions') ， and others that will show trends， like Mailflow status summary， Top Malware， Spoof detections， Compromised users， Mail latency， 保险箱 Links， and 保险箱 attachments reports. 这些指标是自动生成的。|[查看报表](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>后续步骤

[评估 Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

返回到评估 [Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
