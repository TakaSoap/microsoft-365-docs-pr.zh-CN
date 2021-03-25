---
title: Microsoft 365 安全中心概述
description: Microsoft 365 安全中心的优势，将 Microsoft Defender for Office 365 (MDO) 和 Microsoft Defender for Endpoint (MDE) 与 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 相结合。 本文概述了 Microsoft 365 安全中心对管理员的推进。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 02/02/2021
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
ms.openlocfilehash: 3b2e5d834caab9973006eda64e369a2a6aa17b5d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163311"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>统一 Microsoft 365 安全中心概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)

> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中评估它或在](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](m365d-pilot.md?ocid=cx-evalpilot)。

改进的 **Microsoft 365** 安全中心 () 中心门户中对电子邮件、协作、标识和设备威胁的保护、检测、调查和 [https://security.microsoft.com](https://security.microsoft.com) 响应。   

Microsoft 365 安全中心将现有 Microsoft 安全门户（如 Microsoft Defender 安全中心和 Office 365 安全与合规中心）&功能。 安全中心强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。 此中心包括：

- **[Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)** Microsoft Defender for Office 365 通过一组保护电子邮件和 Office 365 资源的预防、检测、调查和搜寻功能帮助组织保护其企业。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为贵组织的设备提供预防性保护、攻破后检测、自动调查和响应。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 扩展检测和响应 *(* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全项目组合自动分析跨域的威胁数据，并生成单个仪表板上攻击的图片。

如果需要有关 Office 365 安全中心或 Microsoft Defender 安全中心&更改的信息，请参阅：

- [Microsoft 365 安全中心中的 Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全中心中的 Defender for Endpoint](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>预期结果

在 Office 365 安全与合规中心 (protection.office.com) 和 Microsoft Defender 安全中心 (securitycenter.microsoft.com) 中使用的所有安全内容现在都可以在 *Microsoft 365* 安全中心找到。

Microsoft 365 安全中心通过将来自不同工作负载的信号融入单个统一体验来帮助安全团队调查和响应攻击：

- 事件&警报
- 搜寻
- 操作中心
- 威胁分析

Microsoft 365 安全中心在将 Microsoft Defender for Office 365 和 Microsoft Defender for Endpoint 合并时强调统一、清晰和共同的目标。 合并基于下面列出的优先级，在不影响每个安全套件为组合提供的功能的情况下进行：

- 公共构建基块
- 常用术语
- 通用实体
- 与其他工作负载的功能奇偶校验

## <a name="unified-investigations"></a>统一调查

简化安全中心可创建一个窗格，用于调查 Microsoft 365 组织内的任何事件。 主要示例是 Microsoft  365 安全中心快速启动上的"事件"节点。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO 中的&quot;事件&quot;页。":::

例如，双击具有高严重性的事件名称，将你带到一个演示聚合中心优势的页面。

![涉及多个终结点上的特权升级的多阶段事件，显示 16 个受影响的设备和 9 个受到影响的用户。](../../media/converged-incident-info-3.png)

> [!TIP]
> 聚合的用户 **选项卡** 是开始查询的一个好位置。 如果你利用聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 MCAS) 以及一系列源（如本地 Active Directory、Azure Active Directory、已同步、本地和第三方用户）的信息，则此单页显示来自聚合工作负载的用户的信息。 详细了解新的 [用户体验](investigate-users.md)。

事件信息显示在受影响的邮箱旁边的用户/标识详细信息和存在风险的设备。 它还关联所有 **调查信息和收集****的证据**。 这使管理员和安全操作团队可以更轻松地从一个高风险警报透视到受影响的用户和邮箱。 查看 **此页面顶部的** "事件"选项卡，此单个位置提供了其他关键安全透视。

> [!IMPORTANT]
> 在特定事件的任何页面顶部，你将看到摘要、警报、设备、用户、**邮箱**、调查和 **证据选项卡。**   

选择 **"** 调查"将打开一个页面，其中显示正在分析的图形，并列出状态 (如等待审批) 修正。 花时间选择环境中的特定事件，深入到这些选项卡，然后实践为不同类型的威胁构建配置文件。 熟悉度将受益于任何稍后的紧急调查。

## <a name="improved-processes"></a>改进的流程

常用控件和内容要么显示在同一位置，要么压缩为一个数据馈送，以便于查找。 例如，统一设置。

### <a name="unified-settings"></a>统一设置

![单击"角色"并打开"设置"页，其中包括常规设置、权限、API 和规则。 打开"权限"，然后打开"角色"。 显示所有角色](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>角色&权限

!["&角色"页显示终结点角色&组、角色和设备组。](../../media/converged-roles-5.png)

 访问 Microsoft 365 安全中心使用 Azure Active Directory 全局角色或自定义角色进行配置。 对于适用于终结点的 Defender，请参阅 [分配用户对 Microsoft Defender 安全中心的访问权限](/microsoft-365/security/defender-endpoint/assign-portal-access)。 对于适用于 Office 365 的 Defender，请参阅 [Microsoft 365 合规中心和 Microsoft 365 安全中心中的权限](../defender-365-security/permissions-microsoft-365-compliance-security.md)。

- 详细了解如何管理对 [Microsoft 365 Defender 的访问权限](m365d-permissions.md)
- 详细了解如何在 Microsoft 365 [安全中心](custom-roles.md) 创建自定义角色

> [!NOTE]
> Microsoft 365 安全中心中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商 [ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 授予访问权限，方式与在 [Microsoft Defender](./mssp-access.md)安全中心授予访问权限的方式相同。

### <a name="integrated-reports"></a>集成报告

Microsoft 365 安全中心也统一了报告。 管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。 此处的链接基于工作负荷配置动态生成。

### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看 Microsoft 365 环境

主页 **显示** 安全团队所需的许多公用卡片。 卡片和数据的组合取决于用户角色。 由于 Microsoft 365 安全中心使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。  

此概览信息可帮助您了解组织中的最新活动。 Microsoft 365 安全中心将来自不同来源的信号汇集在一起，以呈现 Microsoft 365 环境的整体视图。

卡片分为以下类别：

- **标识**- 监视组织中的身份，并跟踪可疑或有风险的行为。 [了解有关标识保护的更多信息](/azure/active-directory/identity-protection/overview-identity-protection)。
- **数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。
- **设备** - 获取有关设备上警报、泄露活动和其他威胁最新信息。
- **应用** - 深入了解在组织中如何使用云应用。 [了解有关 Cloud App Security 发现的应用的更多信息](/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>具有更好的数据覆盖范围的威胁分析
通过以下 Microsoft 365 Defender 威胁分析集成体验跟踪和响应新出现的威胁：

- Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，从而可以跨域进行联合事件管理、自动调查、修正以及主动或被动威胁搜寻。 
- 来自 Microsoft Defender for Office 365 的电子邮件相关检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。
- 威胁相关事件的视图，将警报聚合到跨 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的端到端攻击案例，以减少工作队列，以及简化和加快调查。
- Microsoft 365 Defender 解决方案检测到并阻止的攻击尝试。 还有一些数据可用于推动预防性操作，以缓解进一步暴露的风险并增加恢复能力。 
- 增强型设计，将可操作信息置于聚焦中，帮助你快速识别数据以紧急关注、调查和利用报告。

## <a name="a-centralized-learning-hub"></a>集中式学习中心

Microsoft 365 安全中心包括一个学习中心，从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供正式指导。

在学习中心内，Email & Collaboration (Microsoft Defender for Office 365 或 MDO) 指南与 Endpoint (Microsoft Defender for Endpoint 或 MDE) 以及 Microsoft 365 Defender 学习资源并排提供。

学习中心将打开，学习路径围绕"如何使用 Microsoft 365 Defender 进行调查？"等主题组织。 和"Microsoft Defender for Office 365 最佳做法"。 此部分当前由 Microsoft 内部的安全产品组提供。 每个学习路径反映了了解概念所花的预计时间。 例如，"Microsoft Defender for Office 365 用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且会进行一些有价值的学习。

单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。 To see all Learning paths， click the Show all link in the main panel.

> [!NOTE]
> Microsoft 365 安全中心学习中心顶部有一些有用的筛选器，可让你选择当前为 Microsoft 365 Defender 的产品 (Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365) 。  请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们有多少资源可用于培训和学习。
>
> 除产品筛选器外，还列出了当前主题、 (网络研讨会) 、对安全区域、安全角色和产品功能的熟悉程度或经验。

## <a name="send-us-your-feedback"></a>向我们发送反馈

我们需要你提供反馈。 我们一直在希望改进，因此如果你希望查看某些内容，请将 [你的 Microsoft 365 Defender 反馈发送给我们](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

您还可以从本文留下反馈。 在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或 *"此页面"。*

使用 **"此产品** "按钮获得 *产品* 反馈：

1. 在 *文章* 底部选择"此产品"。
    1. 如果要继续阅读这些方向，请右键单击该按钮，然后单击"在新建选项卡中打开"。
2. 这将导航到 **UserVoice 论坛**。
3. 有 2 个选项：
    1. 向下滚动到文本框 *"我们可以如何在 Office 365* 中提高合规性或更好地保护你的用户？"，并粘贴到 *Microsoft 365 安全中心*。 可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。
    1. 如果确定已报告此问题，并且想要通过投票 (或) ，请使用 UserVoice 右边的"提供反馈"框。  搜索 *Microsoft 365 安全中心*，查找问题，并使用投票 **按钮** 提升其状态。

使用 *此页面* 可就文章本身提供反馈。 感谢您的反馈。 您的声音可帮助我们改进产品。

### <a name="explore-what-the-security-center-has-to-offer"></a>探索安全中心必须提供哪些功能

继续探索 Microsoft 365 安全中心中的特性和功能：

- [管理事件和警报](manage-incidents.md)
- [使用威胁分析跟踪和响应新出现的威胁](threat-analytics.md)
- [操作中心](m365d-action-center.md)
- [跨设备、电子邮件、应用和标识搜索威胁](./advanced-hunting-query-emails-devices.md)
- [自定义检测规则](./custom-detection-rules.md)
- [电子邮件和协作警报](../../compliance/alert-policies.md#default-alert-policies)
- [创建网络钓鱼攻击模拟](../defender-365-security/attack-simulation-training.md)[并创建用于培训团队的有效负载](/microsoft-365/security/defender-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>相关信息
- [Microsoft 365 安全中心](overview-security-center.md)
- [Microsoft 365 安全中心中适用于 Office 365 的 Microsoft Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全中心中的 Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](microsoft-365-security-mde-redirection.md)