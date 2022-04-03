---
title: Microsoft 365 Defender
description: Microsoft 365 Defender是一个协调的威胁防护解决方案，旨在保护设备、标识、数据和应用程序
keywords: MMicrosoft 365 Defender 简介， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
ms.openlocfilehash: 15f4d179d3bc5590e014a15622e462932e8dea7c
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498706"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

Microsoft 365 Defender 是一款统一的漏洞前和漏洞后企业防御套件，结合检测、预防、调查和应急为一体，可针对终结点、标识、电子邮件和应用程序提供集成的保护，抵御复杂的攻击。

借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将其中每个产品接收的威胁信号汇集在一起，并确定威胁的完整范围和影响、进入环境方式、受影响以及威胁当前对组织的影响。 Microsoft 365 Defender采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。

<center><h2>Microsoft 365 Defender 服务</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Defender for Cloud Apps</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender交互式指南

在此交互式指南中，你将了解如何使用Microsoft 365 Defender。 你将看到安全机制Microsoft 365 Defender检测安全风险、调查对组织的攻击以及自动防止有害的活动。

[请查看交互指南](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender保护

Microsoft 365 Defender服务保护：

- **具有 Defender for Endpoint 的终结点** - Defender for Endpoint 是一个统一的终结点平台，用于预防性保护、攻破后检测、自动调查和响应。
- **使用 Defender for Office 365** 的电子邮件和协作 - Office 365 Defender 保护你的组织免受电子邮件、链接 (URL) 和协作工具造成的恶意威胁。
- Identity 为 Defender 的标识和 **Azure Active Directory (Azure AD) Identity Protection** - Defender for Identity 使用你的本地 Active Directory 域服务 (AD DS) 信号来识别、检测和调查针对你的组织的高级威胁、泄露的标识和恶意内部操作。 Azure AD Identity Protection 可自动检测和修正基于云的云中基于标识Azure AD。
- **使用 Microsoft Defender for Cloud Apps** 的应用程序 - 适用于云应用的 Microsoft Defender 是一个全面的跨 SaaS 解决方案，为云应用提供深入了解、强大的数据控制和增强的威胁防护。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww]

Microsoft 365 Defender唯一的跨产品层补充了各个服务组件，以：

- 通过信号共享和自动操作帮助抵御攻击，并协调服务中的防御响应。
- 将警报、可疑事件和受影响资产的数据加入"事件"，为安全团队提供跨产品警报、行为和上下文的攻击的完整情景旁白。
- 通过自动修正触发对受影响资产的自我修复，自动响应泄露。
- 使安全团队能够跨终结点和用户数据执行详细Office搜寻。

下面的示例演示了产品门户如何将Microsoft 365 Defender警报关联到单个事件中。

:::image type="content" source="../../media/overview-incident.png" alt-text="&quot;事件概述&quot;页" lightbox="../../media/overview-incident.png":::

下面是事件的相关警报列表的示例。

:::image type="content" source="../../media/incident-list.png" alt-text="事件警报列表" lightbox="../../media/incident-list.png":::

下面是基于查询的搜索（基于电子邮件和终结点原始数据）的示例。

:::image type="content" source="../../media/advanced-hunting.png" alt-text=" 具有查询详细信息的高级搜寻页面" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender跨产品功能包括：

- **Microsoft 365 Defender** 门户中的跨产品单一窗格 - 有关 Microsoft 365 Defender 门户中单个队列和单个窗格中的检测、受影响资产、自动操作 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">和相关证据的所有信息的中心视图</a>。 
- **组合事件队列** - 通过确保完整攻击范围、受影响的资产和自动修正操作组合在一起并及时出现，帮助安全专业人员重点关注关键方面。 
- **威胁自动响应** - 关键威胁信息在 Microsoft 365 Defender 产品之间实时共享，以帮助阻止攻击进度。 

   例如，如果在受 Defender for Endpoint 保护的终结点上检测到恶意文件，它将指示 Defender for Office 365 扫描该文件并从所有电子邮件中删除该文件。 整个安全套件都会在看到文件时Microsoft 365文件。

- **对损坏** 的设备、用户标识和邮箱进行自我修复 - Microsoft 365 Defender 使用 AI 支持的自动操作和操作手册将受影响的资产修正回安全状态。 Microsoft 365 Defender套件产品的自动修正功能，以确保在可能的情况下自动修正与事件相关的所有受影响资产。
- **跨产品威胁搜寻** - 安全团队可以利用其独特的组织知识，通过针对各种保护产品收集的原始数据创建自己的自定义查询来搜寻泄露的迹象。 Microsoft 365 Defender终结点和 Defender 之间提供对 30 天的历史原始信号和警报数据的基于查询的访问，以Office 365数据。

## <a name="get-started"></a>入门

Microsoft 365 Defender许可要求，然后才能在 Microsoft 365 Defender 门户<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>中启用该服务。有关详细信息，请参阅：

- [许可要求](prerequisites.md#licensing-requirements)
- [打开 Microsoft 365 Defender](m365d-enable.md)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户

该<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>集中了对电子邮件、协作、标识、设备和应用威胁的保护、检测、调查和响应。 

这个单一的窗格将现有 Microsoft 安全门户（如 Microsoft 365 Defender 门户和 Office 365 安全与合规&的功能汇集在一起。 该Microsoft 365 Defender门户强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。 其中包括：

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365可帮助组织通过一组防护、检测、调查和搜寻功能来保护企业，以保护电子邮件Office 365资源。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为贵组织的设备提供预防性保护、攻破后检测、自动调查和响应。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 扩展检测和 *响应 (* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全组合自动分析跨域的威胁数据，并生成单个仪表板上攻击的图片。
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** 是一个全面的跨 SaaS 和 PaaS 解决方案，为云应用提供深入了解、强大的数据控制和增强的威胁防护。

如果需要有关安全与合规中心或 Office 365 门户&更改Microsoft 365 Defender的信息，请参阅：

- [Microsoft 365 Defender 中的 Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender 中的 Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> 该Microsoft 365 Defender门户使用和强制执行现有的基于角色的访问，并且将每个安全模型移动到统一门户。 每个聚合工作负荷都有自己的基于角色的访问。 产品中已有的角色将自动聚合到Microsoft 365 Defender门户。 但是，Microsoft Defender for Cloud Apps 仍将处理自己的角色和权限。

### <a name="what-to-expect"></a>预期结果

现在，可以在 Office 365 安全&中心Microsoft 365安全<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank"></a>中心内使用的所有安全Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">内容</a>。

该Microsoft 365 Defender门户将来自不同工作负载的信号引入一组统一体验，帮助安全团队调查和响应攻击：：

- 事件和警报
- 搜寻
- 操作中心
- 威胁分析

Microsoft 365 Defender合并 Microsoft Defender for Office 365  和 Microsoft Defender for Endpoint 时，它强调统一、清晰和共同的目标。 合并基于下面列出的优先级，在不影响每个安全套件组合提供的功能的情况下进行：

- 常见构建基块
- 常用术语
- 常见实体
- 与其他工作负荷的功能奇偶校验

> [!NOTE]
> 客户无需Microsoft 365 Defender迁移步骤或购买新许可证即可访问 Microsoft 365 Defender 门户。 例如，具有 E3 订阅的管理员可以访问此新门户，就像使用 Microsoft Defender for Office 365 计划 1 和计划 2 的管理员一样;但是，Exchange Online Protection 或 Office 365 计划 1 的 Defender 客户只能看到其订阅许可证支持的安全功能。 门户的目标是集中安全性。

### <a name="unified-investigations"></a>统一调查

集中安全信息可创建一个在安全中心内调查安全Microsoft 365。 主要示例是 **快速** 启动事件&**事件** 下的事件Microsoft 365 Defender。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="事件门户中的&quot;事件Microsoft 365 Defender页" lightbox="../../media/converged-incidents-2.png.png":::

选择事件名称将显示一个页面，该页演示集中化安全信息的价值。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="事件门户中事件的&quot;摘要Microsoft 365 Defender页" lightbox="../../media/converged-incident-info-3.png":::

在事件页面顶部，你将看到摘要、警报、设备、用户、邮箱、调查、证据和响应以及 **Graph选项卡。**  选择这些选项卡可获取更多详细信息。 例如，"用户"选项卡显示聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Defender for Cloud Apps) 以及一系列源（如本地 Active Directory 域服务 (AD DS) 、Azure AD 和第三方标识提供程序）的用户的信息。 有关详细信息，请参阅 [调查用户](investigate-users.md)。

花时间查看环境中的事件，深入了解这些选项卡，并实践了解如何访问为不同类型的威胁的事件提供的信息。

有关详细信息，请参阅[事件Microsoft 365 Defender](incidents-overview.md)。

### <a name="improved-processes"></a>改进的流程

常用控件和内容要么显示在同一位置，要么被压缩为一个数据馈送，以便于查找。 例如，统一设置。

#### <a name="unified-settings"></a>统一设置

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="设置门户中的Microsoft 365 Defender页面" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>角色&权限

:::image type="content" source="../../media/converged-roles-5.png" alt-text="&quot;权限&角色&quot;页上显示的终结点&组" lightbox="../../media/converged-roles-5.png":::

使用Microsoft 365 Defender角色或自定义Azure AD配置对全局角色的访问权限。 对于 Defender for Endpoint，请参阅[向用户分配对 Microsoft 365 Defender 的访问权限](/microsoft-365/security/defender-endpoint/assign-portal-access)。 For Defender for Office 365， see [Permissions in the Microsoft 365 合规中心 and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- 详细了解如何管理[对 Microsoft 365 Defender](m365d-permissions.md)
- 了解有关如何在角色[模板中创建自定义角色](custom-roles.md)Microsoft 365 Defender

> [!NOTE]
> Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商 ([MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 授予访问权限，方式与在 Microsoft 365 Defender 门户中授予访问权限的方式[相同](./mssp-access.md)。

#### <a name="integrated-reports"></a>集成报告

报告中也统一了Microsoft 365 Defender。 管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。 此处的链接基于工作负荷配置动态生成。

#### <a name="quickly-view-your-microsoft-365-environment"></a>快速查看Microsoft 365环境

**主页显示** 安全团队所需的许多公用卡片。 卡片和数据的组合取决于用户角色。 由于Microsoft 365 Defender门户使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。

此概览信息可帮助您了解组织中的最新活动。 Microsoft 365 Defender来自不同源的信号，以呈现环境环境的整体Microsoft 365视图。

卡片分为以下类别：

- **标识** - 监视组织中的身份，并跟踪可疑或有风险的行为。 [详细了解标识保护](/azure/active-directory/identity-protection/overview-identity-protection)。
- **数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。
- **设备** - 获取有关设备上警报、泄露活动和其他威胁最新信息。
- **应用** - 深入了解在组织中如何使用云应用。 [详细了解在 Defender for Cloud Apps 中发现的应用](/cloud-app-security/discovered-apps)。


#### <a name="search-across-entities-preview"></a>跨实体搜索 (预览) 

>[!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。
搜索栏位于页面顶部。 键入时，会提供建议，以便更轻松地查找实体。 增强的搜索结果页面集中了来自所有实体的结果。

可以在 Defender for Endpoint 和 Defender for Identity 中跨以下实体进行搜索： 

- **设备** - 支持 Defender for Endpoint 和 Defender for Identity。 支持使用搜索运算符。 
- **用户** - 支持 Defender for Endpoint、Defender for Identity 和 Defender for Cloud Apps。 
- **文件、IP 和 URL** - 与 Defender for Endpoint 中的功能相同。

    >[!NOTE]
    >IP 和 URL 搜索完全匹配，不会显示在搜索结果页面中 ， 它们直接指向实体页面。 

- **TVM** - 与 Defender for Endpoint 中的相同功能 (漏洞、软件和建议) 。 

 





### <a name="threat-analytics-with-better-data-coverage"></a>具有更好的数据覆盖范围的威胁分析

通过以下集成威胁分析集成体验Microsoft 365 Defender和应对新出现的威胁：

- Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，从而可以跨域进行联合事件管理、自动调查、修正以及主动或被动威胁搜寻。
- 来自 Microsoft Defender for Office 365 电子邮件相关的检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。
- 威胁相关事件的视图，将警报聚合到跨 Microsoft Defender for Endpoint 和 microsoft Defender for Office 365 的端到端攻击案例，以减少工作队列，并简化和加快调查。
- 解决方案检测到并阻止的攻击Microsoft 365 Defender攻击。 还有一些数据可用于推动预防性操作，以缓解进一步暴露的风险并增加恢复能力。
- 增强型设计，将可操作信息置于聚焦中，帮助你快速识别数据以紧急关注、调查和利用报告。

### <a name="a-centralized-learning-hub"></a>集中式Learning中心

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>包括学习中心，从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供正式指导。

在学习中心内，电子邮件&协作 (Microsoft Defender for Office 365) 指南与 Endpoint (Microsoft Defender for Endpoint) 和 Microsoft 365 Defender 学习资源并行提供。

学习中心将打开，Learning主题组织的路径，例如"如何使用 Microsoft 365 Defender？ 和"Microsoft Defender for Office 365最佳做法"。 此部分当前由 Microsoft 内部的安全产品组提供。 每个Learning路径都反映了了解概念所花的预计时间。 例如，"Microsoft Defender for Office 365用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且会进行一些有价值的学习。

单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。 To see all Learning paths， click the Show all link in the main panel.

> [!NOTE]
> 在学习 **中心** 的顶部有一些有用的筛选器Microsoft 365 Defender，你可以从当前 (Microsoft 365 Defender、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365) 中选择产品。 请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们有多少资源可用于培训和学习。
>
> 除产品筛选器外，还列出了当前主题、 (网络研讨会) 、对安全区域、安全角色和产品功能的熟悉程度或经验。

> [!TIP]
> [Microsoft Learn](/learn/) 中有很多其他学习机会。 你将找到认证培训，例如 [MS-500T02-A：实施](/learn/certifications/courses/ms-500t02)威胁Microsoft 365培训。

### <a name="send-us-your-feedback"></a>向我们发送反馈

我们需要你提供反馈。 我们一直在努力改进，因此，如果你希望查看某些内容，请观看此视频，了解如何信任我们阅读 [你的反馈](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

您还可以从本文留下反馈。 在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或" *此页面"*。

使用 **"此产品** "按钮获得 *产品* 反馈：

1. 在 *文章* 底部选择"此产品"。
    1. 如果要继续阅读这些方向，请右键单击该按钮，然后单击"在新建选项卡中打开"。
2. 这将导航到 **UserVoice 论坛**。
3. 有 2 个选项：
    1. 向下滚动到文本框"我们如何提高合规性或更好地保护用户Office 365 *？* 并粘贴 *到Microsoft 365 Defender。* 可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。
    1. 如果确定已报告此问题，并且想要通过投票 (或) ，请使用 UserVoice 右侧"提供反馈"框。 搜索 *Microsoft 365 Defender*，**查找问题，** 然后使用投票按钮提升其状态。

使用 *此页面* 可就文章本身提供反馈。 感谢您的反馈。 您的声音可帮助我们改进产品。

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>了解Microsoft 365 Defender门户必须提供的内容

继续探索以下产品中的Microsoft 365 Defender：

- [管理事件和警报](manage-incidents.md)
- [通过威胁分析跟踪和响应新兴威胁](threat-analytics.md)
- [操作中心](m365d-action-center.md)
- [跨设备、电子邮件、应用和标识搜索威胁](./advanced-hunting-query-emails-devices.md)
- [自定义检测规则](./custom-detection-rules.md)
- [电子邮件和协作警报](../../compliance/alert-policies.md#default-alert-policies)
- [创建网络钓鱼攻击模拟](../office-365-security/attack-simulation-training.md)[并创建用于培训团队的有效负载](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

通过 Microsoft Learn 的此学习路径，你可以Microsoft 365 Defender它如何帮助识别、控制和修正安全威胁。

|培训：|使用 Microsoft 365 Defender 检测和响应网络攻击|
|---|---|
|![Microsoft 365 Defender 训练图标。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender 将跨终结点、标识、电子邮件和应用程序的威胁信号一致，以提供针对复杂网络攻击的集成保护。 Microsoft 365 Defender 是调查和响应事件并主动搜索正在进行的恶意网络安全活动的中心体验。<p> 1 小时 38 分钟 - Learning路径 - 5 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>另请参阅

- [Microsoft 365 Defender 的新增功能](whats-new.md)
- [Microsoft 365 Defender 中的 Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
