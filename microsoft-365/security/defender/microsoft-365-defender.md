---
title: Microsoft 365 Defender
description: Microsoft 365 Defender是一种协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: MMicrosoft 365 Defender 简介，网络安全、高级持久威胁、企业安全、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365-defender
- m365solution-scenario
- m365solution-overview
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c97338121d38650116540564441f3b37051bf05f
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731176"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender 是一款统一的漏洞前和漏洞后企业防御套件，结合检测、预防、调查和应急为一体，可针对终结点、标识、电子邮件和应用程序提供集成的保护，抵御复杂的攻击。

借助集成的Microsoft 365 Defender解决方案，安全专业人员可以将这些产品接收的威胁信号拼接在一起，并确定威胁的完整范围和影响;威胁的进入方式、其影响以及它当前对组织的影响。 Microsoft 365 Defender采取自动操作来防止或停止攻击，并自行治愈受影响的邮箱、终结点和用户标识。

<center><h2>Microsoft 365 Defender 服务</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Defender for Cloud Apps</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender交互式指南

在本交互式指南中，你将了解如何使用Microsoft 365 Defender保护组织。 你将了解Microsoft 365 Defender如何帮助检测安全风险、调查对组织的攻击，以及如何自动防止有害活动。

[请查看交互指南](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender保护

Microsoft 365 Defender服务保护：

- **包含 Defender for Endpoint 的终结点** - Defender for Endpoint 是一个统一的终结点平台，用于预防性保护、违规后检测、自动调查和响应。
- **与Defender for Office 365的电子邮件和协作** - Defender for Office 365保护组织免受电子邮件、链接 (URL) 和协作工具构成的恶意威胁。
- **使用 Defender for Identity 和 Azure Active Directory (Azure AD) Identity Protection 的标识** - Defender for Identity 使用本地 Active Directory域服务 (AD DS) 信号来识别、检测和调查针对你的高级威胁、泄露标识和恶意内部操作 组织。 Azure AD标识保护自动检测和修正基于云的Azure AD中基于标识的风险。
- **具有Microsoft Defender for Cloud Apps的应用程序** - Microsoft Defender for Cloud Apps是一种全面的跨 SaaS 解决方案，可为云应用带来深度可见性、强大的数据控制和增强的威胁防护。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww]

Microsoft 365 Defender独特的跨产品层将各个服务组件增强为：

- 通过信号共享和自动操作帮助防范攻击，并协调服务中的防御性响应。
- 通过将警报、可疑事件和受影响资产的数据加入到"事件"中，讲述安全团队在产品警报、行为和上下文中发生的攻击的完整故事。
- 通过自动修正为受影响的资产触发自我修复，自动响应入侵。
- 使安全团队能够跨终结点和Office数据执行详细而有效的威胁搜寻。

下面是一个示例，说明Microsoft 365 Defender门户如何将产品中的所有相关警报关联到单个事件中。

:::image type="content" source="../../media/overview-incident.png" alt-text="事件概述页" lightbox="../../media/overview-incident.png":::

下面是事件相关警报列表的示例。

:::image type="content" source="../../media/incident-list.png" alt-text="事件的警报列表" lightbox="../../media/incident-list.png":::

下面是基于电子邮件和终结点原始数据的基于查询的搜寻示例。

:::image type="content" source="../../media/advanced-hunting.png" alt-text=" 包含查询详细信息的高级搜寻页" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender跨产品功能包括：

- **Microsoft 365 Defender门户中的跨产品单个玻璃窗格** - 在Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>中，有关检测、受影响资产、自动执行的操作以及相关证据的所有信息的中心视图。 
- **组合事件队列** - 通过确保全面攻击范围、受影响的资产和自动修正操作组合在一起并及时显示，帮助安全专业人员专注于关键事项。 
- **对威胁的自动响应** - 关键威胁信息在Microsoft 365 Defender产品之间实时共享，以帮助阻止攻击的进度。 

   例如，如果在受 Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示Defender for Office 365扫描和删除所有电子邮件中的文件。 整个Microsoft 365安全套件将阻止该文件。

- **针对受损设备、用户标识和邮箱的自我修复** - Microsoft 365 Defender使用 AI 支持的自动操作和 playbook 将受影响的资产修正回安全状态。 Microsoft 365 Defender利用套件产品的自动修正功能，确保尽可能自动修正与事件相关的所有受影响资产。
- **跨产品威胁搜寻** - 安全团队可以利用他们独特的组织知识，通过对各种保护产品收集的原始数据创建自己的自定义查询来寻找妥协的迹象。 Microsoft 365 Defender提供对终结点和Defender for Office 365数据的 30 天历史原始信号和警报数据的基于查询的访问权限。

## <a name="get-started"></a>入门

Microsoft 365 Defender许可要求必须满足，然后才能在Microsoft 365 Defender门户中<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>启用该服务，有关详细信息，请参阅：

- [许可要求](prerequisites.md#licensing-requirements)
- [打开 Microsoft 365 Defender](m365d-enable.md)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>在中心位置结合了对 *电子邮件*、*协作*、*标识*、*设备* 和 *应用* 威胁的保护、检测、调查和响应。

此玻璃窗格将现有 Microsoft 安全门户（如Microsoft 365 Defender门户和Office 365安全&合规中心）的功能汇集在一起。 Microsoft 365 Defender门户强调快速访问信息、更简单的布局，并将相关信息汇集在一起以便更轻松地使用。 其中包括：

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365通过一组预防、检测、调查和搜寻功能来帮助组织保护其企业，以保护电子邮件和Office 365资源。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为组织中的设备提供预防性保护、违规后检测、自动调查和响应。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft *扩展检测和响应* (XDR) 解决方案的一部分，该解决方案利用Microsoft 365安全组合自动分析跨域的威胁数据，并生成针对单个仪表板的攻击的图片。
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** 是一种全面的跨 SaaS 和 PaaS 解决方案，为云应用带来深度可见性、强大的数据控制和增强的威胁防护。

如果需要有关从Office 365安全&合规中心或Microsoft 365 Defender门户更改的信息，请参阅：

- [Microsoft 365 Defender 中的 Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender 中的 Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> Microsoft 365 Defender门户使用并强制实施现有基于角色的访问，并将每个安全模型移动到统一门户。 每个聚合工作负载都有自己的基于角色的访问权限。 产品中已有的角色将自动聚合到Microsoft 365 Defender门户中。 但是，Microsoft Defender for Cloud Apps仍将处理自己的角色和权限。

### <a name="what-to-expect"></a>预期内容

现在可以在Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>中找到Office 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">安全&合规中心</a>和Microsoft 365 安全中心中使用的所有安全内容。

Microsoft 365 Defender门户通过将来自不同工作负荷的信号引入一组统一体验来帮助安全团队调查和响应攻击：

- 事件和警报
- 搜寻
- 操作中心
- 威胁分析

Microsoft 365 Defender在合并Microsoft Defender for Office 365和Microsoft Defender for Endpoint时强调 *团结、明确和共同目标*。 合并基于下面列出的优先级，并且在不牺牲每个安全套件带来的功能的情况下进行了以下组合：

- 常见构建基块
- 常见术语
- 常见实体
- 与其他工作负荷的功能奇偶校验

> [!NOTE]
> 无需客户执行迁移步骤或购买新许可证即可访问Microsoft 365 Defender门户。 例如，具有 E3 订阅的管理员可以访问此新门户，就像具有 Microsoft Defender for Office 365 计划 1 和计划 2 的管理员一样;但是，Exchange Online Protection或Defender for Office 365 计划 1 客户只看到其订阅许可证支持的安全功能。 门户的目标是集中安全性。

### <a name="unified-investigations"></a>统一调查

集中化安全信息可为跨Microsoft 365调查安全事件创建一个位置。 主要 **示例** 是快速启动 **Microsoft 365 Defender时事件&警报** 下的事件。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 Defender门户中的&quot;事件&quot;页" lightbox="../../media/converged-incidents-2.png.png":::

选择事件名称将显示一个演示集中安全信息值的页面。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender门户中事件的摘要页" lightbox="../../media/converged-incident-info-3.png":::

在事件页面顶部，你将看到 **"摘要**"、"**警报**"、"**设备**"、"**用户**"、"**邮箱**"、"**调查**"、"**证据和响应****"和"Graph**"选项卡。 选择这些选项卡以获取更详细的信息。 例如，"**用户**"选项卡显示来自聚合工作负荷 (Microsoft Defender for Endpoint、Microsoft Defender for Identity和Microsoft Defender for Cloud Apps) 以及一系列源的信息，例如本地 Active Directory域服务 (AD DS) 、Azure AD 和第三方标识提供者。 有关详细信息，请参阅 [调查用户](investigate-users.md)。

花时间查看环境中的事件，向下钻取这些选项卡，并练习了解如何访问为不同类型的威胁的事件提供的信息。

有关详细信息，请参阅[Microsoft 365 Defender中的事件](incidents-overview.md)。

### <a name="improved-processes"></a>改进的流程

常见控件和内容要么显示在同一位置，要么压缩为一个数据源，以便更轻松地查找。 例如，统一设置。

#### <a name="unified-settings"></a>统一设置

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="Microsoft 365 Defender门户中的设置页" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>&角色的权限

:::image type="content" source="../../media/converged-roles-5.png" alt-text="&quot;权限&角色&quot;页上显示&组的终结点角色" lightbox="../../media/converged-roles-5.png":::

Azure AD全局角色或使用自定义角色配置对Microsoft 365 Defender的访问权限。 对于 Defender for Endpoint，请参阅[分配用户对Microsoft 365 Defender门户的访问权限](/microsoft-365/security/defender-endpoint/assign-portal-access)。 有关Defender for Office 365，请参阅[Microsoft 365 合规中心和Microsoft 365 Defender中的权限](../office-365-security/permissions-microsoft-365-compliance-security.md)。

- 详细了解如何[管理对Microsoft 365 Defender的访问权限](m365d-permissions.md)
- 详细了解如何在Microsoft 365 Defender中[创建自定义角色](custom-roles.md)

> [!NOTE]
> Microsoft 365 Defender中的Microsoft Defender for Endpoint支持[授予托管安全服务提供商 (MSSP) 的访问权限](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)，就像[在Microsoft 365 Defender门户中授予](./mssp-access.md)访问权限一样。

#### <a name="integrated-reports"></a>集成报表

报表也在Microsoft 365 Defender中统一。 管理员可以从常规安全报告开始，并分支到有关终结点、电子邮件&协作的特定报表。 此处的链接是根据工作负荷配置动态生成的。

#### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看Microsoft 365环境

**主** 页显示安全团队需要的许多常见卡片。 卡片和数据的构成取决于用户角色。 由于Microsoft 365 Defender门户使用基于角色的访问控制，不同角色将看到对日常工作更有意义的卡片。

此概览信息可帮助你跟上组织中的最新活动。 Microsoft 365 Defender汇集来自不同源的信号，以呈现Microsoft 365环境的整体视图。

这些卡属于以下类别：

- **标识** - 监视组织中的标识，并跟踪可疑或有风险的行为。 [详细了解标识保护](/azure/active-directory/identity-protection/overview-identity-protection)。
- **数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。
- **设备** - 获取有关设备上的警报、违规活动和其他威胁的最新信息。
- **应用** - 深入了解如何在组织中使用云应用。 [详细了解Defender for Cloud应用中发现的应用](/cloud-app-security/discovered-apps)。


#### <a name="search-across-entities-preview"></a>跨实体搜索 (预览) 

>[!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。
搜索栏位于页面顶部。 键入时，会提供建议，以便更轻松地查找实体。 增强的搜索结果页集中了来自所有实体的结果。

可以在 Defender for Endpoint 和 Defender for Identity 中搜索以下实体： 

- **设备** - Defender for Endpoint 和 Defender for Identity 都支持。 支持使用搜索运算符。 
- **用户** - Defender for Endpoint、Defender for Identity 和 Defender for Cloud 应用支持。 
- **文件、IP 和 URL** - 与 Defender for Endpoint 中的功能相同。

    >[!NOTE]
    >IP 和 URL 搜索完全匹配，不会显示在搜索结果页中 - 它们直接导致实体页。 

- **TVM** - 与 Defender for Endpoint 中的功能相同 (漏洞、软件和建议) 。 

 





### <a name="threat-analytics-with-better-data-coverage"></a>具有更好数据覆盖率的威胁分析

使用以下Microsoft 365 Defender威胁分析集成体验跟踪和响应新出现的威胁：

- 提高Microsoft Defender for Endpoint和Microsoft Defender for Office 365之间的数据覆盖率，使事件管理、自动调查、修正和跨域主动或被动威胁搜寻成为可能。
- Microsoft Defender for Office 365中的电子邮件相关检测和缓解措施，以及已从Microsoft Defender for Endpoint提供的终结点数据。
- 与威胁相关的事件视图，这些事件将警报聚合到Microsoft Defender for Endpoint和Microsoft Defender for Office 365的端到端攻击事件，以减少工作队列，并简化和加快调查。
- Microsoft 365 Defender解决方案检测到并阻止攻击尝试。 还可以使用一些数据来推动预防性操作，从而降低进一步暴露的风险并提高复原能力。
- 增强的设计，将可操作信息置于聚光灯下，帮助你快速识别数据，以便从报表中紧急关注、调查和利用数据。

### <a name="a-centralized-learning-hub"></a>集中式Learning中心

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>包括一个学习中心，用于从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区和 docs.microsoft.com 的官方文档等资源中获取官方指导。

在学习中心内，电子邮件&协作 (Microsoft Defender for Office 365) 指南与终结点 (Microsoft Defender for Endpoint) 并行，Microsoft 365 Defender学习资源。

学习中心随Learning路径一起打开，这些路径围绕"如何使用Microsoft 365 Defender？ 和"Microsoft Defender for Office 365最佳做法"。 本部分当前由 Microsoft 内的安全产品组策划。 每个Learning路径都反映了完成概念所需的预计时间。 例如，"Microsoft Defender for Office 365用户帐户泄露时要采取的步骤"预计需要 8 分钟，并且非常有用。

单击内容后，将此网站书签并组织到"安全"或"关键"文件夹中可能很有用。 若要查看所有Learning路径，请单击主面板中的"显示所有"链接。

> [!NOTE]
> Microsoft 365 Defender学习中心顶部有有用的 **筛选器**，可让你在当前Microsoft 365 Defender (产品、Microsoft Defender for Endpoint和Microsoft Defender for Office 365) 。 请注意，列出了每个部分的学习资源数，这可以帮助学习者跟踪他们手头有多少用于训练和学习的资源。
>
> 除了产品筛选器之外，还列出了当前主题、从视频到网络研讨会)  (的资源类型、对安全领域、安全角色和产品功能的熟悉程度或体验。

> [!TIP]
> [Microsoft Learn](/learn/) 中有很多其他学习机会。 你将找到认证培训，例如 [MS-500T02-A 课程：实现Microsoft 365威胁防护](/learn/certifications/courses/ms-500t02)。

### <a name="send-us-your-feedback"></a>向我们发送反馈

我们需要你的反馈。 我们一直在寻求改进，因此，如果想要查看某些内容， [请观看此视频，了解如何信任我们阅读反馈](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

还可以保留本文的反馈。 在"提交和查看反馈"的末尾的"反馈"部分中，选项为 *"此产品*"或 *"此页*"。

使用 **"此产品** "按钮进行 *产品* 反馈：

1. 在文章底部选择 *此产品* 。
    1. 如果要继续阅读这些方向，请右键单击按钮和"在新选项卡中打开"。
2. 这会导航到 **UserVoice 论坛**。
3. 有 2 个选项：
    1. 向下滚动到文本框 *，如何在Office 365中更好地提高合规性或保护用户？* 然后粘贴 *Microsoft 365 Defender*。 可以搜索结果以查找类似你的想法并对其进行投票，或使用" **发布新想法"** 按钮。
    1. 如果觉得已报告此问题，并且想要通过投票 (或投票) 来提升其配置文件，请使用 UserVoice 右侧的" *提供反馈* "框。 搜索 *Microsoft 365 Defender*，**查找问题，并使用投票按钮** 提高其状态。

使用 *此页面* 获取有关文章本身的反馈。 感谢你的反馈。 你的声音帮助我们改进产品。

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>了解Microsoft 365 Defender门户提供的内容

继续探索Microsoft 365 Defender中的特性和功能：

- [管理事件和警报](manage-incidents.md)
- [通过威胁分析跟踪和响应新兴威胁](threat-analytics.md)
- [操作中心](m365d-action-center.md)
- [跨设备、电子邮件、应用和标识搜索威胁](./advanced-hunting-query-emails-devices.md)
- [自定义检测规则](./custom-detection-rules.md)
- [电子邮件和协作警报](../../compliance/alert-policies.md#default-alert-policies)
- [创建网络钓鱼攻击模拟](../office-365-security/attack-simulation-training.md) 并 [创建用于训练团队的有效负载](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

借助 Microsoft Learn 的此学习路径，可以了解Microsoft 365 Defender以及它如何帮助识别、控制和修正安全威胁。

|培训：|使用 Microsoft 365 Defender 检测和响应网络攻击|
|---|---|
|![Microsoft 365 Defender 训练图标。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender 将跨终结点、标识、电子邮件和应用程序的威胁信号一致，以提供针对复杂网络攻击的集成保护。 Microsoft 365 Defender 是调查和响应事件并主动搜索正在进行的恶意网络安全活动的中心体验。<p> 1 小时 38 分钟 - Learning路径 - 5 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>另请参阅

- [Microsoft 365 Defender 的新增功能](whats-new.md)
- [Microsoft 365 Defender 中的 Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender中的Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
