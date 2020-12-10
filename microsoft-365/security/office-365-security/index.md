---
title: Office 365 安全性、Microsoft Defender for Office 365、EOP、MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 中的安全性（从 EOP 到 Defender for Office 365 计划1和2）、标准与严格安全配置等。 了解您拥有的功能，以及如何保护属性。
ms.openlocfilehash: 84d7dcfc68ce78bfde92f3d7096cd4104355ce94
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616244"
---
# <a name="office-365-security-overview"></a>Office 365 安全概述

本文将向你介绍云中的新安全属性。 无论您是安全运营中心的一部分，您是安全管理员新的共享空间，还是您需要复习，让我们开始吧。

> [!CAUTION]
> 如果您使用的是 **Outlook.com**、 **microsoft 365 系列** 或 **microsoft 365 个人**，并且需要 *安全链接* 或 *安全附件* 信息，请 ***单击此链接** _： [Microsoft 365 订阅者的高级 Outlook.com 安全性](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="office-365-security-spelled-out"></a>Office 365 安全拼写

每个 Office 365 订阅都附带安全功能。 您可以采取的目标和操作取决于这些不同订阅的重点。 在 Office 365 安全中，有三个主要安全服务 (或产品) 与您的订阅类型关联：

1. Exchange Online Protection (EOP) 
1. Microsoft Defender for Office 365 Plan 1 (Defender for Office P1) 
1. Microsoft Defender for Office 365 Plan 2 (Defender for Office P2) 

> [!NOTE]
> 如果你已购买订阅并需要立即 _right 安全功能 *，请跳转到 [防范威胁](protect-against-threats.md) 一文中的步骤。 如果你不熟悉订阅，并且想要在开始之前了解你的许可证，请在 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/#/homepage)> 你的产品浏览帐单。

Office 365 安全构建在 EOP 提供的核心保护基础之上。 EOP 存在于可在其中找到 Exchange Online 邮箱的任何订阅中， (记住，此处讨论的所有安全产品都是基于云的) 。

您可能习惯查看以这种方式讨论的这三个组件：

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|阻止广泛的、基于卷的已知攻击。|保护电子邮件和协作，从零天的恶意软件、网络钓鱼和业务电子邮件泄露。|为培训) 添加违规后调查、搜寻和响应以及自动化和模拟 (。|
|

但在体系结构方面，让我们先将每个部分视为累积的安全层，每个部分都有安全性重点。 详细信息如下：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 和 Microsoft Defender for Office 365 及其与服务重点之间的关系，包括电子邮件身份验证的说明。":::

虽然这些服务中的每一项都强调了保护、检测、调查和响应等目标，但 **所有** 这些服务都可以执行 _*_任何_*_ 保护、检测、调查和响应的目标。

Office 365 安全性的核心是 EOP 保护。 Microsoft Defender for Office 365 P1 包含 EOP。 适用于 Office 的 Defender 365 P2 包含 P1 和 EOP。 结构是累积的。 这就是为什么在配置此产品时，应从 EOP 开始，并适用于 Office 365 的 Defender。

尽管电子邮件身份验证配置发生在公共 DNS 中，但务必要配置此功能以帮助防御欺骗。 _如果您拥有 EOP，则 **应 [配置电子邮件身份验证](email-validation-and-authentication.md)**_。

如果你有 Office 365 E3 或更低，则可以使用 EOP，但可以选择通过升级为 Office 365 P1 购买独立的 Defender。 如果你有 Office 365 E5，则你已具有适用于 Office 365 P2 的 Defender。

> [!TIP]
> 如果你的订阅既不是 Office 365 E3 或 E5，你仍可以查看是否可以选择升级到 Microsoft Defender for Office 365 P1。 如果您感兴趣， [此网页](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 列出了适用于 Microsoft Defender for Office 365 P1 升级的订阅 (查看页面的结尾) 的打印。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>从 EOP 到 Microsoft Defender for Office 365 的 Office 365 安全阶梯

![EOP 和 Microsoft Defender for Office 365 及其安全性重点，从 "保护和检测" 到 "调查和响应"。 电子邮件身份验证配置 (至少应为 EOP 和 up 设置 DKIM 和 DMARC) 。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 了解以下页面的详细信息： [Exchange Online Protection](exchange-online-protection-overview.md)和 [Defender for Office 365](office-365-atp.md)。

添加 Microsoft Defender for Office 365 计划的好处 EOP 威胁管理的优势乍一眼就很难看出。 若要帮助您确定升级路径是否适合您的组织，让我们来看看每个产品的功能：

- 阻止和检测威胁
- 此处
- 回应

起始为 _ * Exchange Online Protection * *：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括：<ul><li>垃圾邮件 (spam)</li><li>诈骗</li><li>受到</li><li>批量邮件</li><li>欺骗智能</li><li>模拟检测</li><li>管理员隔离</li><li>假阳性和漏报的管理员和用户提交</li><li>允许/阻止 Url 和文件</li><li>报告</li></u1>|<li>审核日志搜索</li><li>邮件跟踪</li>|<li>零小时自动清除 (ZAP) </li><li>"允许" 和 "阻止" 列表的优化和测试</li>|
|

如果您想要深入了解 EOP，请 **[跳转到本文](exchange-online-protection-overview.md)**。

由于这些产品是累积的，因此，如果您评估 Microsoft Defender for Office 365 P1 并决定订阅它，则将添加这些功能。

使用 **适用于 Office 365 的 Defender 的好处，计划 1** (到日期) ：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 和中的所有内容：<u1><li>安全附件</li><li>安全链接<li>Microsoft Defender for Office 365 针对工作负荷的保护 (ex。 SharePoint Online、团队、OneDrive for business) </li><li>电子邮件、Office 客户端和团队中的点击时间保护</li><li>适用于 Office 365 的 Defender 中的反网络钓鱼</li><li>用户和域模拟保护</li><li>警报以及警报的 SIEM 集成 API</li>|<li>用于检测的 SIEM 集成 API</li><li>**实时检测工具**</li><li>URL 跟踪</li>|<li>相同</li></u1>

因此，Microsoft Defender for Office 365 P1 在房子的 **_防御_* 的一侧进行扩展，并添加了额外的 _*_检测_*_ 形式。

Microsoft Defender for Office 365 P1 还添加了适用于调查的 *实时检测**。 此威胁搜寻工具的名称以粗体显示，因为如果 *知道* 你拥有 Office 365 P1 的 Defender，这是一种明确的方法。 它不会显示在 Office 365 P2 的 Defender 中。

使用 **适用于 Office 365 的 Defender，计划 2** (到日期) ：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 中的所有内容，以及 Microsoft Defender for Office 365 P1 plus：<u1><li>相同</li>|<li>**威胁资源管理器**</li><li>威胁跟踪器</li><li>市场活动视图</li>|<li>自动调查和响应 (空中) </li><li>威胁浏览器中的空气</li><li>受损用户的空中</li><li>用于自动调查的 SIEM 集成 API</li>

因此，Microsoft Defender for Office 365 P2 展开在房子的 "*_调查和响应_*" 一侧，并添加新的查找强度。 动画.

在 Microsoft Defender for Office 365 P2 中，将调用主要的搜寻工具 _ *威胁资源管理器** 而不是实时检测。 如果你在导航到安全中心时看到威胁资源管理器，则表示你在 Microsoft Defender for Office 365 P2 中。

若要获取 Microsoft Defender for Office 365 P1 和 P2 的详细信息，请 **[跳转到本文](office-365-atp.md)**。

> [!TIP]
> 对于最终用户而言，EOP 和 Microsoft Defender for Office 365 也是不同的。 在 EOP 和 Defender for Office 365 P1 中，重点是 " *感知*"，因此这两个服务包括 *报告邮件 Outlook 外接程序* ，以便用户可以报告他们感怀疑的电子邮件，以便进一步分析。 <p> 在 Office 365 P2 (其中包含 EOP 和 P1) 中的所有内容，焦点将切换到对最终用户的 *进一步培训* ，因此安全操作中心可以访问功能强大的 *威胁模拟器* 工具以及它提供的最终用户指标。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 计划1与规划2便笺的工作表

此快速参考可帮助您了解每个 Microsoft Defender for Office 365 订阅附带的功能。 与您对 EOP 功能的知识结合使用时，它可以帮助业务决策者确定哪种 Microsoft Defender for Office 365 最适合自己的需求。

|适用于 Office 的 Defender 365 计划1|适用于 Office 的 Defender 365 计划2|
|---|---|
|配置、保护和检测功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全链接](atp-safe-links.md)</li><li>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 中的反网络钓鱼保护](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[实时检测](threat-explorer.md)</li></ul>|适用于 Office 365 的 Defender 计划1功能 <p> --- + --- <p> 自动化、调查、补救措施和教育功能： <ul><li>[威胁跟踪器](threat-trackers.md)</li><li>[威胁资源管理器](threat-explorer.md)</li><li>[自动调查和响应](office-365-air.md)</li><li>[攻击模拟器](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 计划2包含在 Office 365 E5、Office 365 A5 和 Microsoft 365 E5 中。

- Microsoft Defender for Office 365 计划1包含在 Microsoft 365 商业高级版中。

- Microsoft Defender for Office 365 Plan 1 和 Defender for Office 365 计划2每个都可用作特定订阅的加载项。 若要了解详细信息，请 [在 Microsoft Defender For Office 365 计划](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)中提供另一个链接功能可用性。

- " [安全文档](safe-docs.md) " 功能仅适用于使用 Microsoft 365 E5 或 Microsoft 365 e5 安全许可证的用户 (不包含在 microsoft Defender for Office 365 计划) 中。

- 如果你的当前订阅不包含 Microsoft Defender for Office 365，并且你想要它，请 [联系 sales 以开始试用](https://go.microsoft.com/fwlink/p/?LinkId=518644)，并了解 Microsoft Defender for Office 365 如何在你的组织中工作。

> [!TIP]
> ***内幕提示** _。 您可以使用 docs.microsoft.com 目录了解 EOP 和 Microsoft Defender for Office 365。 导航回此页面（ [Office 365 安全概述](https://docs.microsoft.com/microsoft-365/security/office-365-security)），您会注意到侧面栏中的目录组织。 它从部署 (开始，包括迁移) ，然后继续进入预防、检测、调查和响应。 <p> 此结构进行了划分，以便 *安全管理** 主题遵循 **安全操作** 主题。 如果您是工作角色的一个新成员，请使用此提示中的链接和您对目录的了解，以帮助了解空间。 请记住使用 *反馈链接* 并在转到时对 *文章打分* 。 反馈可帮助我们改进我们为你提供的内容。

## <a name="where-to-go-next"></a>下一步转到何处

如果你是安全管理员，你可能需要为你的邮件配置 DKIM 或 DMARC。 您可能希望为优先级用户实施 "严格" 安全预设，或查找产品中的新增功能。 如果你使用的是安全操作，你可能需要利用实时检测或威胁资源管理器来调查和响应，或使用攻击模拟器对最终用户检测进行培训。 无论哪种方式，下面都提供了有关下一步要查看的其他建议。

[电子邮件身份验证，包括 SPF、DKIM 和 DMARC (，其中包含所有三个) 的设置的链接 ](email-validation-and-authentication.md)

[查看特定建议的 "黄金"](recommended-settings-for-eop-and-office365-atp.md) 配置，并 [使用其建议预设快速配置安全策略](preset-security-policies.md)

追赶 [Microsoft Defender For Office 365 中的新增功能 (包括 EOP 发展) ](whats-new-in-office-365-atp.md)

[使用威胁资源管理器或实时检测](threat-explorer.md)

[在 Microsoft Defender For Office 365 中使用攻击模拟器](attack-simulator.md)
