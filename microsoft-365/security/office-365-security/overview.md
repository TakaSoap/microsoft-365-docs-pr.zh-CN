---
title: Office 365安全，包括适用于 Office 365 和 Exchange Online Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/21/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Office 365 中的安全性, 从 EOP 到 Defender for Office 365 计划 1 和 2, 标准与严格安全配置等。 了解自己拥有的财产以及如何保护财产。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20bb1dcf9c34f0f7507d8fec7c9025de03461533
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317019"
---
# <a name="microsoft-defender-for-office-365-security-overview"></a>Microsoft Defender for Office 365安全概述

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

本文将向你介绍新的 Microsoft Defender for Office 365云中的安全属性。 无论你是安全运营中心的一员，还是该领域的新手，还是想要复习一下，让我们开始吧。

> [!CAUTION]
> 如果你使用的是 **Outlook.com**、**Microsoft 365 家庭版** 或 **Microsoft 365 个人版**，并且需要 *安全链接* 或 *安全附件* 信息，***单击此链接***：[适用于 Microsoft 365 订阅者的高级 Outlook.com 安全机制](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="what-is-defender-for-office-365-security"></a>什么是 Defender for Office 365 安全

每一 Office 365 订阅都具有安全功能。 目标和可以采取的行动取决于这些不同订阅的重点。 在 Office 365 安全中，三种主要的安全服务（或产品）与你的订阅类型相关联：

1. Exchange Online Protection (EOP)
1. Microsoft Defender for Office 365 计划 1（Defender for Office 计划 1）
1. Microsoft Defender for Office 365 计划 2（Defender for Office 计划 2）

> [!NOTE]
> 如果购买了订阅，并且需要 *立即* 推出安全功能，请跳至 [抵御威胁​​](protect-against-threats.md)一文中的步骤。 如果第一次使用订阅，并且想在开始之前了解许可证，请在 [Microsoft 365 管理员中心](https://admin.microsoft.com/AdminPortal/#/homepage)中浏览账单 > 你的产品。

Office 365 安全基于 EOP 提供的核心保护创建。 EOP 可用于可找到 Exchange Online 邮箱的任何订阅（请记住此处讨论的所有安全产品均基于云）。

你可能已经习惯了以这种方式讨论这三个组件：

|EOP|Microsoft Defender for Office 365 计划 1|Microsoft Defender for Office 365 计划 2|
|---|---|---|
|防止广泛的、基于批量的已知攻击。|保护电子邮件和协作免受零日恶意软件、网络钓鱼和企业电子邮件的危害。|添加了漏洞后调查、搜索和响应，以及自动化和模拟（用于培训）。|
|

但是在架构方面，让我们开始将每个部分视为安全的累积层，每层都强调安全性。 更多此类内容：

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP 和 Microsoft Defender for Office 365 以及与其他的关系，重点是服务，其中包括有关电子邮件身份验证的说明。":::

虽然每个服务都强调"保护、检测、调查"和"响应"中的一个目标，但 ***所有** _ 服务可以执行 _ *_任何_** 目标，如保护、检测、调查以及响应。

Office 365 安全性的核心是 EOP 保护。 Microsoft Defender for Office 365 P1 中包含 EOP。 Defender for Office 365 P2 中包含 P1 和 EOP。 结构是累积的。 因此，配置此产品时，应先从 EOP 开始，然后是 Defender for Office 365。

虽然电子邮件身份验证配置是在公共 DNS 中进行，但配置此功能有助于防御欺骗至关重要。 *如果拥有 EOP ，* ***应 [配置电子邮件身份验证](email-validation-and-authentication.md)***。

如果拥有 Office 365 E3 或更低版本，则拥有 EOP，但可以选择通过升级购买单机版 Defender for Office 365 计划 1。 如果拥有 Office 365 E5，则已经拥有 Defender for Office 365 计划 2。

> [!TIP]
> 如果订阅不是 Office 365 E3 或 E5，仍可查看是否可选择升级到 Microsoft Defender for Office 365 计划 1。 如果有兴趣，[此网页](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids)列出有资格获得 Microsoft Defender for Office 365 计划 1升级的订阅（有关详细信息，请查看附属细则页面的末尾）。

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>从 EOP 到 Microsoft Defender for Office 365 的 Office 365 安全阶梯

> [!IMPORTANT]
> 了解以下页面的详细信息：[Exchange Online Protection](exchange-online-protection-overview.md)和 [Defender for Office 365](defender-for-office-365.md)。

初看起来，很难说出为 Microsoft Defender for Office 365 计划对纯 EOP 威胁管理具有优势的原因。 为帮助整理升级路径是否适合你的组织，我们来了解一下每个产品在以下方面的功能：

- 阻止和检测威胁
- 正在调查
- 响应

从 **Exchange Online Protection** 开始：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括：<ul><li>垃圾邮件</li><li>网络钓鱼</li><li>恶意软件</li><li>批量邮件</li><li>欺骗智能</li><li>模拟检测</li><li>管理员隔离</li><li>管理员和用户的"误报"和"漏报"提交</li><li>允许/阻止 URL 和文件</li><li>报告</li></ul>|<li>审核日志搜索</li><li>邮件跟踪</li>|<li>零时差自动清除 (ZAP) </li><li>允许列表和阻止列表精简和测试</li>|
|

如果您想深入了解EOP，请 **[跳至本文](exchange-online-protection-overview.md)**。

由于这些产品是累积性的，因此，如果评估 Microsoft Defender for Office 365 计划 1 并决定订阅此产品，则将添加这些功能。

使用 **Defender for Office 365 计划 1** 获得收益（最新版本）：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 中的所有内容及：<ul><li>安全附件</li><li>安全链接<li>适用于工作负载的 Microsoft Defender for Office 365 保护（例如 SharePoint Online、Teams、OneDrive for Business）</li><li>电子邮件、Office 客户端和 Teams 中的单击时间保护</li><li>Defender for Office 365 中的防钓鱼</li><li>用户和域模拟保护</li><li>警报和用于警报的 SIEM 集成 API</li>|<li>用于检测的 SIEM 集成 API</li><li>**实时检测工具**</li><li>URL 跟踪</li>|<li>相同</li></ul>

因此，Microsoft Defender for Office 365 计划 1 * **预防** _侧进行了扩展，并添加了_ * _检测_ **的其他形式。

Microsoft Defender for Office 365 计划 1 还添加了 **实时检测** 以进行调查。 此威胁搜寻工具的名称为粗体，因为清楚地 *知道* 你拥有 Defender for Office 365 计划 1。 它不显示在 Defender for Office 365 计划 2 中。

使用 **Defender for Office 365 计划 2** 获得收益（最新版本）：
<p>

|阻止/检测|调查|响应|
|---|---|---|
|技术包括 EOP 中的所有内容和 Microsoft Defender for Office 365 计划 1 及：<ul><li>相同</li>|<li>**威胁资源管理器**</li><li>威胁跟踪器</li><li>市场活动视图</li>|<li>自动调查和响应 (AIR)</li><li>威胁资源管理器 AIR</li><li>被盗用户 AIR</li><li>用于自动化调查的 SIEM 集成 API</li>

因此，Microsoft Defender for Office 365 计划 2 在 ***调查和响应*** 方面进行了扩展，并增加了新的搜寻功能。 自动化。

在 Microsoft Defender for Office 365 计划 2 中，主要的搜索工具称为 **威胁浏览器** 而不是实时检测。 如果你在导航到安全中心门户时看到威胁资源管理器Microsoft 365 Defender，则你已使用 Microsoft Defender for Office 365 P2。

如果深入了解 Microsoft Defender for Office 365 计划 1 和 2，请 **[跳至本文](defender-for-office-365.md)**。

> [!TIP]
> 对于最终用户，EOP 和 Microsoft Defender for Office 365 也有所不同。 在EOP 和 Defender for Office 365 计划 1中，重点是 *意识*，因此这两项服务包括 *报告邮件 Outlook 加载项*，以便用户可以报告发现可疑的电子邮件，进行进一步分析。 <p> 在 Defender for Office 365 计划 2（包含 EOP 和计划 1中的所有内容）中，重点转移到了最终用户 *进一步培训*，因此安全操作中心可以使用功能强大的 *威胁模拟器* 工具以及它提供的最终用户指标。

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 计划 1 与计划 2 速查表

此快速参考将帮助您了解 Microsoft Defender for Office 365 订阅附带的功能。 结合对 EOP 功能的了解，可以帮助业务决策者确定最适合需要的 Microsoft Defender for Office 365。

|Defender for Office 365 计划 1|Defender for Office 365 计划 2|
|---|---|
|配置、保护和检测功能： <ul><li>[安全附件](safe-attachments.md)</li><li>[安全链接](safe-links.md)</li><li>[用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 中的防钓鱼保护](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[实时检测](threat-explorer.md)</li></ul>|Defender for Office 365 计划 1 功能 <p> --- + --- <p> 自动化、调查、补救措施和教育功能： <ul><li>[威胁跟踪器](threat-trackers.md)</li><li>[威胁资源管理器](threat-explorer.md)</li><li>[自动调查和响应](office-365-air.md)</li><li>[攻击模拟培训](attack-simulation-training.md)</li><li>[通过高级搜寻主动搜寻Microsoft 365 Defender](../defender/advanced-hunting-overview.md)</li><li>[调查事件Microsoft 365 Defender](../defender/investigate-incidents.md)</li><li>[调查警报Microsoft 365 Defender](../defender/investigate-alerts.md)</li></ul>|

- Office 365 E5、Office 365 A5 和 Microsoft 365 E5 中包含 Microsoft Defender for Office 365 计划 2。

- Microsoft Defender for Office 365 计划 1 包含在 Microsoft 365 商业高级版中。

- Microsoft Defender for Office 365 计划 1 和 Defender for Office 365 计划 2 均可用作特定订阅的加载项。 若要了解详细信息，请参阅另一个链接[Microsoft Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 只有拥有 Microsoft 365 E5 或 Microsoft 365 E5 安全性许可证（未包括在 Microsoft Defender for Office 365 计划内）的用户才能使用[安全文档](safe-docs.md)功能。

- 如果你当前的订阅不包括 Microsoft Defender for Office 365 并希望订阅，请[与销售人员联系以开始试用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)，并了解 Defender for Office 365 如在你的组织使用。

- Microsoft Defender for Office 365 P2 客户有权访问 **Microsoft 365 Defender 集成** 以有效检测、查看和响应事件和警报。

> [!TIP]
> ***预览体验成员提示** _。 可以使用 docs.microsoft.com 目录，以了解 EOP和 Microsoft Defender for Office 365。 浏览回到此页面，[Office 365 安全性概览](index.yml)，会在侧栏中注意到目录组织。 它从部署（包括迁移）开始，然后继续进行预防、检测、调查和响应。 <p> 此结构进行了划分，因此_ *安全管理** 主题后面是 **安全操作** 主题。 如果你是任一工作角色的新成员，请使用此提示中的链接以及你对目录的知识来帮助了解工作空间。 记住随时随地使用 *反馈链接* 和 *评价文章*。 反馈有助于我们改进所提供的服务。

## <a name="where-to-go-next"></a>下一步要访问的位置

如果你是安全管理员，则可能需要针对邮件配置 DKIM 或 DMARC。 可能想为优先级用户推出“严格”安全性预设，或者寻找产品中的新功能。 或者，如果使用安全操作，可能想要利用实时检测或威胁资源管理器进行调查并响应，或者使用"攻击模拟器"系统对最终用户检测进行培训。 无论哪种方式，这里都有一些其他建议，供你进一步参考。

[电子邮件身份验证，包括 SPF、DKIM 和 DMARC（带有指向所有这三种设置的链接）](email-validation-and-authentication.md)

[查看特定的推荐“黄金”配置](recommended-settings-for-eop-and-office365.md)和[使用推荐的预设来快速配置安全策略](preset-security-policies.md)

查看 [Microsoft Defender for Office 365 的新增功能（包括 EOP 开发）](whats-new-in-defender-for-office-365.md)

[使用威胁资源管理器（或实时检测）](threat-explorer.md)

使用 [攻击模拟培训](attack-simulation-training.md)
