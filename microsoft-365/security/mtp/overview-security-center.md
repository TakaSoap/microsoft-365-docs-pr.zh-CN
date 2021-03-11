---
title: Microsoft 365 安全中心概述
description: Microsoft 365 安全中心的优势，将 Microsoft Defender for Office 365 (MDO) 和 Microsoft Defender for Endpoint (MDE) 与 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 相结合。 本文概述了针对管理员的 Microsoft 365 安全中心发展。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视器， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 87149ab9c99168d62f5114555a46b8bfaee83ab2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712098"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>统一 Microsoft 365 安全中心概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> 想要体验 Microsoft 365 Defender？ 可以在 [实验室环境中对其进行评估，](https://aka.ms/mtp-trial-lab) 或在生产中 [运行您的试验项目](https://aka.ms/m365d-pilotplaybook)。

改进的 **Microsoft 365** 安全中心 () 集中了对电子邮件、协作、标识和设备威胁的保护、检测、调查和 [https://security.microsoft.com](https://security.microsoft.com) 响应。    

Microsoft 365 安全中心将现有 Microsoft 安全门户（如 Microsoft Defender 安全中心和 Office 365 安全与合规中心）&功能。 安全中心强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。 此中心包括：

- **[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 通过一组保护电子邮件和 Office 365 资源的防护、检测、调查和搜寻功能帮助组织保护其企业。
- **[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 为组织中设备提供预防性保护、泄露后检测、自动调查和响应。
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** 是 Microsoft 扩展检测和响应 *(* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全组合自动分析跨域的威胁数据，在单个仪表板上生成攻击图片。

如果需要有关 Office 365 安全与合规中心或 Microsoft Defender 安全中心&更改的信息，请参阅：

- [Microsoft 365 安全中心中的 Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全中心中的 Defender for Endpoint](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>预期结果

现在可以在 Microsoft 365 安全中心找到你在 Office 365 安全与合规中心 (protection.office.com) 和 Microsoft Defender 安全中心 (securitycenter.microsoft.com) 中使用的所有安全 *内容*。

Microsoft 365 安全中心通过将来自不同工作负载的信号融入单个统一体验来帮助安全团队调查和响应攻击：

- 事件&警报
- 搜寻
- 操作中心
- 威胁分析

Microsoft 365 安全中心在将 Microsoft Defender for Office 365 和 Microsoft Defender for Endpoint 合并时强调统一、清晰和共同的目标。 合并基于下面列出的优先级，在不影响每个安全套件组合提供的功能的情况下进行：

- 常见构建基块
- 常用术语
- 通用实体
- 与其他工作负载的功能奇偶校验

## <a name="unified-investigations"></a>统一调查

简化安全中心可创建一个窗格，用于调查 Microsoft 365 组织内的任何事件。 主要示例是 Microsoft  365 安全中心快速启动上的"事件"节点。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO 中的&quot;事件&quot;页。":::

例如，双击高严重性事件名称将你带到一个演示聚合中心优势的页面。

![涉及多个终结点上的特权提升的多阶段事件，显示 16 个受影响的设备和 9 个受影响的用户。](../../media/converged-incident-info-3.png)

> [!TIP]
> 聚合用户 **选项卡** 是开始查询的一个好位置。 如果利用聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 MCAS，则此单页显示用户的信息（如果利用) 以及一系列源，如本地 Active Directory、Azure Active Directory、同步用户、本地和第三方用户）。 详细了解新的 [用户体验](investigate-users.md)。

事件信息显示在受影响的邮箱旁边的用户/标识详细信息和存在风险的设备。 它还关联任何 **调查信息和** 收集 **的证据**。 这使管理员和安全操作团队可以更轻松地将一个高风险警报透视给受影响的用户和邮箱。 查看 **此页面顶部的"** 事件"选项卡，此单个位置提供了其他关键安全透视。

> [!IMPORTANT]
> 在特定事件的任何页面顶部，你将看到摘要、警报、设备、**用户**、**邮箱**、调查和 **证据选项卡。**   

选择 **"** 调查"将打开一个页面，该页面包含正在分析的图形，并列出了一个 (，例如等待审批) 修正。 花时间选择环境中的特定事件，深入了解这些选项卡，并实践为不同类型的威胁构建配置文件。 熟悉度将有利于以后的任何按下调查。

## <a name="improved-processes"></a>改进的流程

常用控件和内容显示在同一位置，或压缩为一个数据馈送，使其更易于查找。 例如，统一设置。

### <a name="unified-settings"></a>统一设置

![单击"角色"并打开"设置"页，其中包括常规设置、权限、API 和规则。 打开"权限"，然后打开"角色"。 显示所有角色](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>角色&权限

![显示&组、角色和设备&终结点角色的"角色"页。](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. 对于 Defender for Endpoint，请参阅["分配用户对 Microsoft Defender 安全中心的访问权限"。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) 对于 Defender for Office 365，请参阅 [Microsoft 365 合规中心和 Microsoft 365 安全中心中的权限](../office-365-security/permissions-microsoft-365-compliance-security.md)。

- 详细了解如何管理对 [Microsoft 365 Defender 的访问权限](mtp-permissions.md)
- 详细了解如何在 Microsoft 365 [安全中心](custom-roles.md) 创建自定义角色

### <a name="integrated-reports"></a>集成报告

Microsoft 365 安全中心也统一了报告。 管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。 此处的链接基于工作负载配置动态生成。

### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看 Microsoft 365 环境

主页 **显示** 安全团队所需的许多公用卡片。 卡片和数据的组合取决于用户角色。 由于 Microsoft 365 安全中心使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。  

此概览信息可帮助您了解组织中的最新活动。 Microsoft 365 安全中心将来自不同源的信号汇集在一起，以呈现 Microsoft 365 环境的整体视图。

卡片分为以下类别：

- **标识**- 监视组织中的身份，并跟踪可疑或有风险的行为。 [了解有关标识保护的信息](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。
- **数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。
- **设备** - 获取有关警报、泄露活动以及设备上的其他威胁最新信息。
- **应用** - 深入了解在组织中如何使用云应用。 [了解有关云应用安全发现的应用的信息](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>具有更好的数据覆盖范围的威胁分析
通过以下 Microsoft 365 Defender 威胁分析集成体验跟踪和响应新出现的威胁：

- Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，使跨域联合事件管理、自动调查、修正以及主动或被动威胁搜寻成为可能。 
- Microsoft Defender for Office 365 中的电子邮件相关检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。
- 威胁相关事件的视图，这些事件将警报聚合到 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的端到端攻击情景中，以减少工作队列，并简化和加快调查。
- Microsoft 365 Defender 解决方案检测到并阻止的攻击尝试。 还有一些数据可用于推动预防性操作，从而降低进一步曝光的风险并增加恢复能力。 
- 增强型设计，将可操作信息置于聚焦中，帮助你快速识别要紧急关注、调查和利用报告的数据。

## <a name="a-centralized-learning-hub"></a>集中式学习中心

Microsoft 365 安全中心包括一个学习中心，该学习中心从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供官方指导。

在学习中心内，电子邮件 & 协作 (Microsoft Defender for Office 365 或 MDO) 指南与 Endpoint (Microsoft Defender for Endpoint 或 MDE) 以及 Microsoft 365 Defender 学习资源并行提供。

学习中心将打开，学习路径围绕诸如"如何使用 Microsoft 365 Defender 进行调查？"等主题组织。 和"Microsoft Defender for Office 365 最佳做法"。 本部分当前由 Microsoft 内部的安全产品组进行设计。 每个学习路径反映了了解概念所花的预计时间。 例如，"Microsoft Defender for Office 365 用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且非常有价值。

单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。 若要查看所有学习路径，请单击主面板中的"显示所有链接"。

> [!NOTE]
> Microsoft 365 安全中心学习中心顶部有一些有用的筛选器，可让你在产品之间选择 (当前 Microsoft 365 Defender、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365) 。  请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们可用于培训和学习的资源数量。
>
> 除了产品筛选器外，还列出了当前主题、 (视频到网络研讨会) 的资源类型、安全区域、安全角色和产品功能的熟悉程度或体验。

## <a name="send-us-your-feedback"></a>向我们发送反馈

我们需要你的反馈。 我们一直在寻求改进，因此如果你希望看到某些内容，请将 [你的 Microsoft 365 Defender 反馈发送给我们](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

您还可以从本文中留下反馈。 在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或 *"此页面"。*

使用 **"此产品** "按钮获得 *产品* 反馈：

1. 在 *文章* 底部选择此产品。
    1. 若要继续阅读这些方向，请右键单击该按钮并"打开新选项卡"。
2. 这将导航到 **UserVoice 论坛**。
3. 有 2 个选项：
    1. 向下滚动到文本框 *，我们可以如何在 Office 365* 中改进合规性或更好地保护用户？并粘贴到 *Microsoft 365 安全中心*。 可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。
    1. 如果确定已报告此问题，并且希望通过投票 (或) 来提升其配置文件，请使用 UserVoice 右侧"提供反馈"框。  搜索 *Microsoft 365* 安全中心，查找问题，并使用投票 **按钮** 来提升其状态。

使用 *此页面* 可就文章本身提供反馈。 感谢您的反馈。 您的声音可帮助我们改进产品。

### <a name="explore-what-the-security-center-has-to-offer"></a>了解安全中心提供哪些功能

继续探索 Microsoft 365 安全中心中的特性和功能：

- [管理事件和警报](manage-incidents.md)
- [通过威胁分析跟踪和响应新出现的威胁](threat-analytics.md)
- [操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [跨设备、电子邮件、应用和标识搜寻威胁](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [自定义检测规则](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [电子邮件&协作警报](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [创建网络钓鱼攻击模拟并](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training)[创建用于培训团队的有效负载](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>相关信息
- [Microsoft 365 安全中心](overview-security-center.md)
- [Microsoft 365 安全中心中的 Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 安全中心中的 Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](microsoft-365-security-mde-redirection.md)
