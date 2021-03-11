---
title: Office 365 安全、Microsoft Defender for Office 365、EOP、MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 中的安全性，从 EOP 到适用于 Office 365 计划 1 和 2 的 Defender，Standard 与严格安全配置等。 了解你拥有哪些属性以及如何保护你的属性。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711936"
---
# <a name="office-365-security-overview"></a>Office 365 安全概述

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)


本文将向你介绍云中的新安全属性。 无论你是安全操作中心的一员，你是空间的新安全管理员，还是想要刷新，让我们开始吧。

> [!CAUTION]
> 如果你使用的是 **Outlook.com、Microsoft** **365** 家庭版或 Microsoft **365 个人** 版，并且需要安全链接或安全 *附件* 信息，请单击此链接：Microsoft [365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)订阅者的高级 Outlook.com 安全。

## <a name="office-365-security-spelled-out"></a>拼写了 Office 365 安全

每个 Office 365 订阅都附带了安全性功能。 可以采取的目标和操作取决于这些不同订阅的焦点。 在 Office 365 安全性中，有三种与订阅 (或) 绑定的主要安全服务：

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 计划 1 (Defender for Office P1) 
1. Microsoft Defender for Office 365 计划 2 (Defender for Office P2) 

> [!NOTE]
> 如果你购买了订阅，并且需要现在推出安全功能，请跳到"防范威胁["文章中](protect-against-threats.md)的步骤。 如果你是订阅的新增用户，并且想在开始之前了解你的许可证，> [Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage)管理中心浏览你的产品的帐单。

Office 365 安全基于 EOP 提供的核心保护。 EOP 存在于任何订阅中，其中 Exchange Online 邮箱 (，此处讨论的所有安全产品都是基于云的) 。

你可能习惯这样看到讨论这三个组件：

|EOP|Microsoft Defender for Office 365 P1|Microsoft Defender for Office 365 P2|
|---|---|---|
|防止广泛、基于卷的已知攻击。|保护电子邮件和协作免受零日恶意软件、网络钓鱼和商业电子邮件入侵的侵害。|添加泄露后调查、搜寻和响应，以及自动化和模拟 (培训) 。|
|

但就体系结构而言，我们首先考虑每个部分作为累积安全层，每个层都强调安全性。 更类似：

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 和 Microsoft Defender for Office 365 及其彼此之间的关系，其中强调服务，包括电子邮件身份验证说明。":::

尽管其中每个服务都强调保护、检测、调查和响应中的一个目标，但 ***所有** _ 服务都可以 *_执行保护、_* 检测、调查和响应的任何 * 目标。

Office 365 安全的核心是 EOP 保护。 Microsoft Defender for Office 365 P1 包含 EOP。 Defender for Office 365 P2 包含 P1 和 EOP。 结构是累积的。 这就是为什么在配置此产品时，你应该从 EOP 开始，然后使用适用于 Office 365 的 Defender。

尽管电子邮件身份验证配置发生在公共 DNS 中，但配置此功能以帮助防御欺骗很重要。 *如果您有 EOP，****应 [配置电子邮件身份验证](email-validation-and-authentication.md)***。

如果你有 Office 365 E3 或以下版本，你有 EOP，但可以选择通过升级为 Office 365 P1 购买独立 Defender。 如果你有 Office 365 E5，则你已经拥有适用于 Office 365 P2 的 Defender。

> [!TIP]
> 如果你的订阅不是 Office 365 E3 或 E5，你仍可以检查你能否选择升级到 Microsoft Defender for Office 365 P1。 如果你感兴趣，此网页将[](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)列出符合 Microsoft Defender for Office 365 P1 升级 (检查页面末尾是否具有打印) 。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>从 EOP 到 Microsoft Defender for Office 365 的 Office 365 安全中心

![EOP 和 Microsoft Defender for Office 365 及其安全重点，从保护和检测到调查和响应。 至少 (EOP 和) 设置 DKIM 和 DMARC 身份验证配置。](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> 了解这些页面上的详细信息[：Exchange Online Protection](exchange-online-protection-overview.md)和 Defender for Office [365。](office-365-atp.md)

添加 Microsoft Defender for Office 365 计划对纯 EOP 威胁管理的优势可能很难一目了然。 为了帮助确定升级路径是否适合贵组织，我们来看看每种产品的功能：

- 防止和检测威胁
- 正在调查
- 响应

从 **Exchange Online Protection 开始**：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括：<ul><li>垃圾邮件 (spam)</li><li>phish</li><li>恶意软件</li><li>批量邮件</li><li>欺骗智能</li><li>模拟检测</li><li>管理员隔离</li><li>误报和误报的管理员和用户提交</li><li>允许/阻止 URL 和文件</li><li>报表</li></u1>|<li>审核日志搜索</li><li>邮件跟踪</li>|<li>零时差自动清除 (ZAP) </li><li>允许列表和阻止列表的精简和测试</li>|
|

如果要深入了解 EOP， **[请跳转到本文](exchange-online-protection-overview.md)**。

由于这些产品是累积的，因此如果你评估 Microsoft Defender for Office 365 P1 并决定订阅它，你将添加这些功能。

到目前为止 **，Defender for Office 365 计划 1** (获得) ：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 中所有内容以及：<u1><li>安全附件</li><li>安全链接<li>适用于工作负载的 Microsoft Defender for Office 365 (例如 SharePoint Online、Teams、OneDrive for Business) </li><li>电子邮件、Office 客户端和 Teams 中的点击时间保护</li><li>Defender for Office 365 中的防钓鱼</li><li>用户和域模拟保护</li><li>警报和适用于警报的 SIEM 集成 API</li>|<li>用于检测的 SIEM 集成 API</li><li>**实时检测工具**</li><li>URL 跟踪</li>|<li>相同</li></u1>

因此，Microsoft Defender for Office 365 P1 在房间的 ***保护** _ 侧展开，并添加 __*_ 检测 **的额外形式。

Microsoft Defender for Office 365 P1 **还添加了** 调查实时检测。 此威胁搜寻工具的名称以粗体显示，因为拥有它明显意味着了解你拥有适用于 Office 365 P1 的 Defender。 它不会在 Defender for Office 365 P2 中显示。

到目前为止 **，Defender for Office 365 计划 2** (获得) ：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 和 Microsoft Defender for Office 365 P1 中所有功能以及：<u1><li>相同</li>|<li>**威胁资源管理器**</li><li>威胁跟踪器</li><li>市场活动视图</li>|<li>AIR (自动调查和) </li><li>来自威胁资源管理器的 AIR</li><li>针对受损用户的 AIR</li><li>用于自动调查的 SIEM 集成 API</li>

因此，Microsoft Defender for Office 365 P2 扩展了内部调查和响应端，并添加了新的搜寻强度。  自动化。

在 Microsoft Defender for Office 365 P2中，主要搜寻工具称为威胁资源管理器，而不是实时检测。 如果你在导航到安全中心时看到威胁资源管理器，你将在 Microsoft Defender for Office 365 P2 中。

若要了解适用于 Office 365 P1 和 P2 的 Microsoft Defender 的详细信息， **[请跳转到本文](office-365-atp.md)**。

> [!TIP]
> 对于最终用户，EOP 和 Microsoft Defender for Office 365 也有所不同。 在 EOP 和 Defender for Office 365 P1 中，焦点是感知，因此这两项服务包括报告邮件 *Outlook* 外接程序，以便用户可以报告他们发现可疑的电子邮件，以便进一步分析。 <p> 在 Defender for Office 365 P2 (其中包含 EOP 和 P1) 中所有内容中，重点转移到针对最终用户的进一步培训，因此安全操作中心可以访问功能强大的威胁模拟器工具及其提供的最终用户指标。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 计划 1 与计划 2 的欺骗工作表

本快速参考将帮助您了解每个 Microsoft Defender for Office 365 订阅提供的功能。 结合你对 EOP 功能的知识，它可以帮助业务决策者确定最适合其需求的 Microsoft Defender for Office 365。

|Defender for Office 365 计划 1|Defender for Office 365 计划 2|
|---|---|
|配置、保护和检测功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全链接](atp-safe-links.md)</li><li>[用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 中的防钓鱼保护](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[实时检测](threat-explorer.md)</li></ul>|Defender for Office 365 计划 1 功能 <p> --- + --- <p> 自动化、调查、补救措施和教育功能： <ul><li>[威胁跟踪器](threat-trackers.md)</li><li>[威胁资源管理器](threat-explorer.md)</li><li>[自动调查和响应](office-365-air.md)</li><li>[攻击模拟器](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 计划 2 包含在 Office 365 E5、Office 365 A5 和 Microsoft 365 E5 中。

- Microsoft Defender for Office 365 计划 1 包含在 Microsoft 365 商业高级版中。

- Microsoft Defender for Office 365 计划 1 和 Defender for Office 365 计划 2 均作为特定订阅的加载项提供。 若要了解更多信息，下面是 Microsoft [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)计划之间的另一个链接功能可用性。

- 只有拥有 Microsoft 365 E5 或 Microsoft 365 E5 安全性许可证（未包括在 Microsoft Defender for Office 365 计划内）的用户才能使用[安全文档](safe-docs.md)功能。

- 如果你的当前订阅不包括 Microsoft Defender for Office 365，并且你想要它[](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)，请联系销售部门开始试用，了解 Microsoft Defender for Office 365 在组织中如何工作。

> [!TIP]
> ***预览体验成员提示** _. 可以使用目录docs.microsoft.com了解 EOP 和 Microsoft Defender for Office 365。 导航回此页面 [，即 Office 365](index.md)安全概述，你将注意到侧栏中的目录组织。 它首先部署部署 (迁移) ，然后继续进入预防、检测、调查和响应。 <p> 此结构分为两部分，以便 _ *Security Administration** 主题后跟 **安全操作** 主题。 如果你是任一工作角色的新增成员，请使用此提示中的链接以及你了解的目录，以帮助了解空间。 请记住， *在继续时* 使用反馈 *链接和评分* 文章。 反馈可帮助我们改进我们为您提供的信息。

## <a name="where-to-go-next"></a>下一步将转到何处

如果你是安全管理员，可能需要为邮件配置 DKIM 或 DMARC。 你可能想要为优先用户推出"严格"安全预设，或查找产品中的新增功能。 或者，如果你使用安全操作，你可能想要利用实时检测或威胁资源管理器来调查和响应，或者使用攻击模拟器训练最终用户检测。 无论使用哪种方式，下面是有关下一步要查看哪些项的一些其他建议。

[电子邮件身份验证，包括 SPF、DKIM 和 DMARC (包含所有三种身份验证设置) ](email-validation-and-authentication.md)

[查看特定的推荐"黄金"](recommended-settings-for-eop-and-office365-atp.md) 配置，并使用其建议的预设快速 [配置安全策略](preset-security-policies.md)

了解适用于[Office 365 的 Microsoft Defender 365](whats-new-in-office-365-atp.md) (新增功能，包括 EOP) 

[使用威胁资源管理器或实时检测](threat-explorer.md)

在 [Microsoft Defender for Office 365 中使用攻击模拟器](attack-simulator.md)
