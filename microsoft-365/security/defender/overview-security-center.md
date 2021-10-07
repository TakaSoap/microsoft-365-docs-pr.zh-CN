---
title: Microsoft 365 Defender，组合 MDO、MDE、MDI 和 MCAS
description: Microsoft 365 Defender的优势，将适用于 Office 365 (MDO) 的 Microsoft Defender 与适用于 Endpoint (MDE) 的 Microsoft Defender 与 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 结合使用。 本文概述了Microsoft 365 Defender的一些进展。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: a0dce3a61847924043a10df4c13c963f279ea011
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162286"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Defender概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。

**Microsoft 365 Defender ()** 集中了对电子邮件、协作、标识和设备威胁的保护、检测、调查和 [https://security.microsoft.com](https://security.microsoft.com) 响应。    

Microsoft 365 Defender将现有 Microsoft 安全门户（如 Microsoft Defender 安全中心 和 Office 365 安全与合规&的功能汇集在一起。 安全中心强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。 此中心包括：

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365通过一组防护、检测、调查和搜寻功能帮助组织保护其企业，以保护电子邮件Office 365资源。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为贵组织的设备提供预防性保护、攻破后检测、自动调查和响应。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 扩展检测和响应 *(* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全项目组合自动分析跨域的威胁数据，并生成单个仪表板上攻击的图片。

如果需要有关安全与合规中心Office 365更改&的信息，请参阅Microsoft Defender 安全中心：

- [Microsoft 365 Defender 中的 Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender 中的 Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> 安全Microsoft 365门户使用和强制执行现有的基于角色的访问，并且将每个安全模型移动到统一门户。 每个聚合工作负荷都有自己的基于角色的访问。 产品中已有的角色将自动聚合到Microsoft 365门户。 但是，MCAS 的角色和权限仍将在 MCAS 中处理。

## <a name="what-to-expect"></a>预期结果

现在，可以在 Office 365 安全与合规中心 (protection.office.com) 和 Microsoft Defender 安全中心 (securitycenter.microsoft.com) 中 *Microsoft 365 Defender。*

Microsoft 365 Defender将来自不同工作负载的信号引入一组统一体验，帮助安全团队调查和响应攻击：：

- 事件和警报
- 搜寻
- 操作中心
- 威胁分析

Microsoft 365 Defender合并 Microsoft  Defender for Office 365 和 Microsoft Defender for Endpoint 时，它强调统一、清晰和共同的目标。 合并基于下面列出的优先级，在不影响每个安全套件组合提供的功能的情况下进行：

- 常见构建基块
- 常用术语
- 常见实体
- 与其他工作负荷的功能奇偶校验

> [!NOTE]
> Microsoft 365 Defender无需客户执行迁移步骤或购买新许可证即可访问。 例如，具有 E3 订阅的管理员可以访问这个新门户，就像使用 Microsoft Defender for Office 365 计划 1 和计划 2 的管理员一样;但是，Exchange Online Protection计划 1 Office 365 Defender 将仅看到其订阅许可证支持的安全功能。 新中心的目标是集中安全性。

## <a name="unified-investigations"></a>统一调查

聚合安全中心为调查整个安全中心的安全事件Microsoft 365。 主要示例是 **事件** 下的事件 **&快速启动** 事件时发出警报Microsoft 365 Defender。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="事件页面中的&quot;事件Microsoft 365 Defender。":::

选择事件名称将显示一个页面，该页面演示聚合安全中心的价值。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="事件摘要页中事件的示例Microsoft 365 Defender":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender.](../../media/converged-incident-info-3.png)
--> 

在事件页面顶部，你将看到摘要、警报、设备、**用户**、**邮箱**、调查和 **证据** 选项卡。    选择这些选项卡可获取更多详细信息。 例如，"用户"选项卡显示聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security) 以及一系列源（如本地 Active Directory 域服务 (AD DS) 、Azure Active Directory (Azure AD) 和第三方标识提供程序）的用户的信息。 有关详细信息，请参阅 [调查用户](investigate-users.md)。

花时间查看环境中的事件，深入了解这些选项卡，并实践了解如何访问为不同类型的威胁的事件提供的信息。

有关详细信息，请参阅[事件Microsoft 365 Defender。](incidents-overview.md)

## <a name="improved-processes"></a>改进的流程

常用控件和内容要么显示在同一位置，要么被压缩为一个数据馈送，以便于查找。 例如，统一设置。

### <a name="unified-settings"></a>统一设置

![单击"角色"并打开设置页面，其中包括常规设置、权限、API 和规则。 打开"权限"，然后打开"角色"。 显示所有角色。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>角色&权限

!["&角色"页显示终结点角色&组、角色和设备组。](../../media/converged-roles-5.png)

 使用Microsoft 365 Defender角色或自定义Azure Active Directory配置对全局角色的访问权限。 对于 Defender for Endpoint，请参阅[分配用户对 Microsoft Defender 安全中心](/microsoft-365/security/defender-endpoint/assign-portal-access)的访问权限。 For Defender for Office 365， see [Permissions in the Microsoft 365 合规中心 and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- 详细了解如何管理[对](m365d-permissions.md)Microsoft 365 Defender
- 了解有关如何在角色[模板中创建自定义角色](custom-roles.md)Microsoft 365 Defender

> [!NOTE]
> Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商[ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)授予访问权限，方式与在 Microsoft Defender 安全中心 中授予访问权限[的方式相同](./mssp-access.md)。

### <a name="integrated-reports"></a>集成报告

报告中也统一了Microsoft 365 Defender。 管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。 此处的链接基于工作负荷配置动态生成。

### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看Microsoft 365环境

主页 **显示** 安全团队所需的许多公用卡片。 卡片和数据的组合取决于用户角色。 由于Microsoft 365 Defender门户使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。  

此概览信息可帮助您了解组织中的最新活动。 Microsoft 365 Defender来自不同源的信号，以呈现环境环境的整体Microsoft 365视图。

卡片分为以下类别：

- **标识**- 监视组织中的身份，并跟踪可疑或有风险的行为。 [了解有关标识保护的更多信息](/azure/active-directory/identity-protection/overview-identity-protection)。
- **数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。
- **设备** - 获取有关设备上警报、泄露活动和其他威胁最新信息。
- **应用** - 深入了解在组织中如何使用云应用。 [了解有关已发现云应用安全应用的信息](/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>具有更好的数据覆盖范围的威胁分析
通过以下威胁分析集成体验Microsoft 365 Defender和应对新出现的威胁：

- Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，从而可以跨域进行联合事件管理、自动调查、修正以及主动或被动威胁搜寻。 
- 来自 Microsoft Defender for Office 365 电子邮件相关的检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。
- 威胁相关事件的视图，可跨 Microsoft Defender for Endpoint 和 microsoft Defender for Office 365 将警报聚合到端到端攻击案例，以减少工作队列，以及简化和加快调查。
- 解决方案检测到并阻止的攻击Microsoft 365 Defender攻击。 还有一些数据可用于推动预防性操作，以缓解进一步暴露的风险并增加恢复能力。 
- 增强型设计，将可操作信息置于聚焦中，帮助你快速识别数据以紧急关注、调查和利用报告。

## <a name="a-centralized-learning-hub"></a>集中式Learning中心

Microsoft 365 Defender门户包括学习中心，从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供正式指导。

在学习中心内，电子邮件&协作 (Microsoft Defender for Office 365) 指南与 Endpoint (Microsoft Defender for Endpoint) 和 Microsoft 365 Defender 学习资源并排提供。

学习中心将打开，Learning主题组织的路径，例如"如何使用 Microsoft 365 Defender？ 和"Microsoft Defender for Office 365最佳做法"。 此部分当前由 Microsoft 内部的安全产品组提供。 每个Learning路径都反映了了解概念所花的预计时间。 例如，"Microsoft Defender for Office 365用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且会进行一些有价值的学习。

单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。 To see all Learning paths， click the Show all link in the main panel.

> [!NOTE]
> 在 **学习中心的顶部** 有一些有用的筛选器Microsoft 365 Defender，你可以从当前 (、Microsoft Defender for Endpoint Microsoft 365 Defender 和 Microsoft Defender for Office 365) 进行选择。 请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们有多少资源可用于培训和学习。
>
> 除产品筛选器外，还列出了当前主题 (从视频到网络研讨会) 的资源类型、对安全区域、安全角色和产品功能的熟悉程度或体验。

> [!TIP]
> Microsoft Learn 中有很多其他 [学习机会](/learn/)。 你将找到认证培训，例如[MS-500T02-A：实施Microsoft 365威胁防护。](/learn/certifications/courses/ms-500t02)

## <a name="send-us-your-feedback"></a>向我们发送反馈

我们需要你提供反馈。 我们一直在努力改进，因此如果你希望看到一些内容，请将你的反馈Microsoft 365 Defender[我们](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

您还可以从本文留下反馈。 在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或 *"此页面"。*

使用 **"此产品** "按钮获得 *产品* 反馈：

1. 在 *文章* 底部选择"此产品"。
    1. 如果要继续阅读这些方向，请右键单击该按钮，然后单击"在新建选项卡中打开"。
2. 这将导航到 **UserVoice 论坛**。
3. 有 2 个选项：
    1. 向下滚动到文本框"我们如何提高合规性或更好地保护用户 *Office 365？* 并粘贴 *到Microsoft 365 Defender"*。 可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。
    1. 如果确定已报告此问题，并且想要通过投票 (或) ，请使用 UserVoice 右边的"提供反馈"框。  搜索 *Microsoft 365 Defender，***查找问题，** 并使用投票按钮提升其状态。

使用 *此页面* 可就文章本身提供反馈。 感谢您的反馈。 您的声音可帮助我们改进产品。

### <a name="explore-what-the-security-center-has-to-offer"></a>探索安全中心必须提供哪些功能

继续探索以下功能中的Microsoft 365 Defender：

- [管理事件和警报](manage-incidents.md)
- [通过威胁分析跟踪和响应新兴威胁](threat-analytics.md)
- [操作中心](m365d-action-center.md)
- [跨设备、电子邮件、应用和标识搜索威胁](./advanced-hunting-query-emails-devices.md)
- [自定义检测规则](./custom-detection-rules.md)
- [电子邮件和协作警报](../../compliance/alert-policies.md#default-alert-policies)
- [创建网络钓鱼攻击模拟](../office-365-security/attack-simulation-training.md)[并创建用于培训团队的有效负载](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>相关信息
- [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [将帐户从 Microsoft Defender for Endpoint 重定向到Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)