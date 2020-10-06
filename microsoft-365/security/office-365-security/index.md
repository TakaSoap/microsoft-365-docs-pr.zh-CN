---
title: Office 365 安全性、Office 365 ATP、EOP、ATP、MSDO
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
description: Office 365 中的安全性（从 EOP 到 ATP 计划1和2）、标准和严格安全配置等。 了解您拥有的功能，以及如何保护属性。
ms.openlocfilehash: c5b357dc7a08eeef099b25172169d04cdb81e8c4
ms.sourcegitcommit: 5abd5ef8c2903b4c3bd875da68049fde26768dcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2020
ms.locfileid: "48359149"
---
# <a name="office-365-security-overview"></a>Office 365 安全概述

本文将向你介绍云中的新安全属性。 无论您是安全运营中心的一部分，您是安全管理员新的共享空间，还是您需要复习，让我们开始吧。

> [!CAUTION]
> 你好。 如果您使用的 **是 Outlook.com**、 **microsoft 365 系列**或 **microsoft 365 个人**版，并且需要 *安全链接* 或 *安全附件* 信息，请 ***单击此链接***： [Microsoft 365 订阅者的高级 Outlook.com 安全性](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。 归功!

## <a name="office-365-security-spelled-out"></a>Office 365 安全拼写

每个 Office 365 订阅都附带安全功能。 您可以采取的目标和操作取决于这些不同订阅的重点。 在 Office 365 安全中，有三个主要安全服务 (或产品) 与您的订阅类型关联：

1. Exchange Online Protection (EOP) 
1. 高级威胁防护，计划 1 (ATP P1) 
1. 高级威胁防护，规划 2 (ATP P2) 

> [!NOTE]
> 如果你已购买订阅，并且需要 *立即*推出安全功能，请跳转到 [抵御威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 一文中的步骤。 如果你不熟悉订阅，并且想要在开始之前了解你的许可证，请在 [Microsoft 365 管理中心](https://admin.microsoft.com/AdminPortal/#/homepage)> 你的产品浏览帐单。

Office 365 安全构建在 EOP 提供的核心保护基础之上。 EOP 存在于可在其中找到 Exchange Online 邮箱的任何订阅中， (记住，此处讨论的所有安全产品都是基于云的) 。

您可能习惯查看以这种方式讨论的这三个组件：

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|阻止广泛的、基于卷的已知攻击。    |  保护电子邮件和协作，从零天的恶意软件、网络钓鱼和业务电子邮件泄露。       | 为培训) 添加违规后调查、搜寻和响应以及自动化和模拟 (。         |

但在体系结构方面，让我们先将每个部分视为累积的安全层，每个部分都有安全性重点。 详细信息如下：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

虽然这些服务中的每一项都强调了保护、检测、调查和响应等目标，但 ***所有*** 服务都可以执行 ***任何*** 保护、检测、调查和响应的目标。

Office 365 安全性的核心是 EOP 保护。 ATP P1 包含 EOP 中的。 ATP P2 包含 P1 和 EOP。 结构是累积的。 这就是为什么在配置此产品时，应从 EOP 开始，并工作到 ATP。

尽管电子邮件身份验证配置发生在公共 DNS 中，但务必要配置此功能以帮助防御欺骗。 *如果您有 EOP，* ***则应 [配置电子邮件身份验证](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)***。

如果你有 Office 365 E3 或更低，则可以使用 EOP，但可以选择通过升级购买独立的 ATP P1。 如果您有 Office 365 E5，则您已具有 ATP P2。

> [!TIP]
> 如果您的订阅既不是 Office 365 E3 或 E5，您仍可以查看是否有升级到 ATP P1 的选项。 如果你感兴趣， [此网页](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) 将列出符合 ATP P1 升级 (的订阅。若要查看页面的结尾) ，请查看页面的结尾。

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>从 EOP 到 ATP 的 Office 365 安全阶梯

<br/>

![EOP 和 ATP 以及它们的安全性重点，从 "保护和检测" 到调查和响应。电子邮件身份验证配置 (至少应为 EOP 和 up 设置 DKIM 和 DMARC) 。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> 了解有关这些页面的详细信息： [Exchange Online protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)和 [高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)。

添加 ATP 计划的好处是，EOP 威胁管理的优势在第一眼中很难看出。 若要帮助您确定升级路径是否适合您的组织，让我们来看看每个产品的功能：

 - 阻止和检测威胁
 - 此处
 - 回应

从 **Exchange Online Protection**开始：
<p>

|阻止/检测  |调查  |响应  |
|---------|---------|---------|
| 技术包括：<ul><li>垃圾邮件 (spam)</li><li>诈骗</li><li>受到</li><li>批量邮件</li><li>欺骗智能</li><li>模拟检测</li><li>管理员隔离</li><li>假阳性和漏报的管理员和用户提交</li><li>允许/阻止 Url 和文件</li><li>报告</li></u1>|<li>审核日志搜索</li><li>邮件跟踪</li>|<li>零小时自动清除 (ZAP) </li><li>"允许" 和 "阻止" 列表的优化和测试</li>|

如果您想要深入了解 EOP，请 **[跳转到本文](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**。

由于这些产品是累积的，因此，如果你评估 ATP P1 并决定订阅它，你将添加这些功能。

通过 **高级威胁防护获得收益，Plan 1** (截止到目前为止) ：
<p>

|阻止/检测  |调查  |响应  |
|---------|---------|---------|
| 技术包括 EOP 和中的所有内容：<u1><li>安全附件</li><li>安全链接<li>针对工作负载的 ATP 保护 (ex。 SharePoint Online、团队、OneDrive for business) </li><li>电子邮件、Office 客户端和团队中的点击时间保护</li><li>ATP 反网络钓鱼</li><li>用户和域模拟保护</li><li>警报以及警报的 SIEM 集成 API</li>|<li>用于检测的 SIEM 集成 API</li><li>**实时检测工具**</li><li>URL 跟踪</li>|<li>相同</li></u1>

因此，ATP P1 在房子的 ***防止*** 一侧进行扩展，并添加了额外的 ***检测***形式。

ATP P1 也会为调查添加 **实时检测** 。 此威胁搜寻工具的名称以粗体显示，因为如果 *知道* 你有 ATP P1，这是一种明确的方法。 它不会显示在 ATP P2 中。

通过 **高级威胁防护获得收益，Plan 2** (截止到目前为止) ：
<p>

|阻止/检测  |调查  |响应  |
|---------|---------|---------|
| 这些技术包括 EOP 中的所有内容和 ATP P1 plus：<u1><li>相同</li>|<li>**威胁资源管理器**</li><li>威胁跟踪器</li><li>市场活动视图</li>|<li>自动调查和响应 (空中) </li><li>威胁浏览器中的空气</li><li>受损用户的空中</li><li>用于自动调查的 SIEM 集成 API</li>

因此，ATP P2 会在公司的 ***调查和响应*** 方面展开，并添加新的搜寻强度。 动画.

在 ATP P2 中，主要搜寻工具称为 **威胁浏览器** ，而不是实时检测。 如果你在导航到安全中心时看到威胁资源管理器，则是在 ATP P2 中。

若要获取 ATP P1 和 P2 的详细信息，请 **[跳转到本文](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**。

> [!TIP]
> 对于最终用户而言，EOP 和 ATP 也是不同的。 在 EOP 和 ATP P1 中，焦点是 " *感知*"，因此这两个服务包括 *报告邮件 Outlook 外接程序* ，以便用户可以报告他们认为可疑的电子邮件，以便进一步分析。 <p> 在 ATP P2 (包含 EOP 和 P1) 中的所有内容时，焦点将转到针对最终用户的 *进一步培训* ，因此安全操作中心可以访问功能强大的 *威胁模拟器* 工具以及它所提供的最终用户指标。

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP 计划1与规划2便笺的工作表

此快速参考可帮助您了解每个 ATP 订阅附带的功能。 与您对 EOP 功能的知识结合使用时，它可以帮助业务决策者确定哪种 ATP 最适合自己的需求。

|Office 365 ATP 计划 1|Office 365 ATP 计划 2|
|---|---|
|<br/>配置、保护和检测功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全链接](atp-safe-links.md)</li><li>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)</li><li>[ATP 防钓鱼保护](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[实时检测](threat-explorer.md)</li></ul>|Office 365 ATP 计划 1 功能<br/>--- + ---<br/>自动化、调查、补救措施和教育功能：</li><li>[威胁跟踪器](threat-trackers.md)</li><li>[威胁资源管理器](threat-explorer.md)</li><li>[自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[攻击模拟器](attack-simulator.md)</li></ul>|
|

- Office 365 E5、Office 365 A5 和 Microsoft 365 E5 中包含 Office 365 ATP 计划 2。

- Office 365 ATP 计划 1 包含在 Microsoft 365 商业高级版中。

- Office 365 ATP 计划 1 和 Office 365 ATP 计划 2 可各自用作特定订阅的加载项。 若要了解详细信息，请 [在 ATP 计划](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)中提供另一个链接功能可用性。

- 只有拥有 Microsoft 365 E5 或 Microsoft 365 E5 安全版许可证（未包括在 Office 365 ATP 计划内）的用户才能使用[安全文档](safe-docs.md)功能。

- 如果当前订阅不包含 Office 365 ATP，并且您需要它，请 [联系 sales 以开始试用](https://go.microsoft.com/fwlink/p/?LinkId=518644)，并了解 ATP 在您的组织中如何工作。

> [!TIP]
> ***内幕提示***。 您可以使用 docs.microsoft.com 目录了解 EOP 和 ATP。 导航回此页面（ [Office 365 安全概述](https://docs.microsoft.com/microsoft-365/security/office-365-security/?view=o365-worldwide)），您会注意到侧面栏中的目录组织。 它从部署 (开始，包括迁移) ，然后继续进入预防、检测、调查和响应。 <p> 将划分此结构，以便 **安全管理** 主题遵循 **安全操作** 主题。 如果您是工作角色的一个新成员，请使用此提示中的链接和您对目录的了解，以帮助了解空间。 请记住使用 *反馈链接* 并在转到时对 *文章打分* 。 反馈可帮助我们改进我们为你提供的内容。

## <a name="where-to-go-next"></a>下一步转到何处

如果你是安全管理员，你可能需要为你的邮件配置 DKIM 或 DMARC。 您可能希望为优先级用户实施 "严格" 安全预设，或查找产品中的新增功能。 如果你使用的是安全操作，你可能需要利用实时检测或威胁资源管理器来调查和响应，或使用攻击模拟器对最终用户检测进行培训。 无论哪种方式，下面都提供了有关下一步要查看的其他建议。

[电子邮件身份验证，包括 SPF、DKIM 和 DMARC (，其中包含所有三个) 的设置的链接 ](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[查看特定建议的 "黄金"](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 配置，并 [使用其建议预设快速配置安全策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

[了解 Office 365 ATP (中的新增功能，包括 EOP 发展) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

[使用威胁资源管理器或实时检测](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

使用 [Office 365 ATP 中的攻击模拟器](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)