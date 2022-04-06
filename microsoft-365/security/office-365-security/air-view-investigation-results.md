---
title: 查看自动调查的结果Microsoft 365
keywords: AIR， autoIR， Microsoft Defender for Endpoint， 自动化， 调查， 修正， 操作
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在系统自动调查期间Microsoft 365，您可以查看结果和关键发现。
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bf9fe34a88444d9d8ec6dccf4b22a507e55dfb00
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680789"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>自动调查的详细信息和Microsoft 365

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

当 [Microsoft](office-365-air.md) [Defender for Office 365](defender-for-office-365.md)自动调查时，可在自动调查过程中和之后获得有关该调查的详细信息。 如果您具有必要的权限，可以在管理门户中查看这些Microsoft 365 Defender详细信息。 调查详细信息为您提供了最新状态以及批准任何挂起操作的能力。

> [!TIP]
> 查看企业门户中新的统一调查Microsoft 365 Defender页面。 有关详细信息，请参阅" [ 新建 (统一) 页](../defender/m365d-autoir-results.md#new-unified-investigation-page)。

## <a name="investigation-status"></a>调查状态

调查状态指示分析和操作的进度。 在调查运行时，状态会发生变化，以指示是否已发现威胁，以及是否已批准操作。

|状态|说明|
|---|---|
|**即将开始**|已触发调查并等待开始运行。|
|**正在运行**|调查过程已开始，正在进行中。 当挂起的操作得到批准时 [，也会发生](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) 此状态。|
|**未找到威胁**|调查已完成，未 (用户帐户、电子邮件、URL 或文件) 威胁。 <p> **提示**：如果怀疑某些内容 (漏报（如漏报) ，可以使用威胁 [资源管理器采取措施](threat-explorer.md)。|
|**发现威胁**|自动调查发现了问题，但没有具体的修正操作来解决这些问题。 <p> 当 **标识了** 某种类型的用户活动但没有可用的清理操作时，可能会发生"已发现威胁"状态。 示例包括以下任一用户活动： <ul><li>[数据丢失防护](../../compliance/dlp-learn-about-dlp.md)事件</li><li>电子邮件发送异常</li><li>已发送恶意软件</li><li>已发送钓鱼邮件</li></ul> <p> 该调查未发现要修正的恶意 URL、文件或电子邮件，也没有要修复的邮箱活动，例如关闭转发规则或委派。 <p> **提示**：如果怀疑某些内容 (漏报，例如漏报) ，可以使用威胁资源管理器进行调查并 [采取措施](threat-explorer.md)|
|**已由系统终止**|调查已停止。 调查可能会因多种原因停止： <ul><li>调查的挂起操作已过期。 等待审批一周后挂起的操作将退出</li><li>操作过多。 例如，如果单击恶意 URL 的用户过多，可能会超出调查运行所有分析器的能力，因此调查将停止</li></ul> <p> **提示**：如果调查在操作之前停止，请尝试使用威胁资源管理器查找 [](threat-explorer.md)并解决威胁。|
|**挂起的操作**|调查已发现一个威胁（如恶意电子邮件、恶意 URL 或存在风险邮箱设置）以及一项修正该威胁的操作正在等待 [审批](air-review-approve-pending-completed-actions.md)。 <p> 当 **找到具有** 相应操作的任何威胁时，将触发挂起的操作状态。 但是，随着调查的运行，挂起操作的列表可能会增加。 查看调查详细信息，查看其他项目是否仍等待完成。|
|**已修正**|调查已完成，并且所有修正操作均 (完全修正) 。 <p> **注意**：已批准的修正操作可能会出现错误，阻止采取这些操作。 无论修正操作是否成功完成，调查状态都不会改变。 查看调查详细信息。|
|**部分修正**|调查的结果是修正操作，其中一些已获得批准并已完成。 其他操作仍处于挂起 [状态](air-review-approve-pending-completed-actions.md)。|
|**失败**|至少有一个调查分析器遇到了无法正确完成的问题。 <p> **注意** 如果在修正操作获得批准后调查失败，则修正操作可能仍成功。 查看调查详细信息。|
|**按限制排队**|正在队列中进行调查。 其他调查完成后，将开始排队调查。 限制有助于避免服务性能不佳。  <p> **提示**：挂起的操作可以限制可以运行的新调查数量。 确保批准 [或拒绝 (挂起) 操作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)。|
|**已终止限制**|如果队列中的调查时间太长，将停止。 <p> **提示**：你可以 [从威胁资源管理器开始调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。|

## <a name="view-details-of-an-investigation"></a>查看调查的详细信息

1. 转到"Microsoft 365 Defender门户 () <https://security.microsoft.com> 并登录。
2. 在导航窗格中，选择操作 **中心**。
3. 在"挂起 **"或** " **历史记录"** 选项卡上，选择一个操作。 将打开其飞出窗格。
4. 在飞出窗格中，选择" **打开调查页面"**。 
5. 使用各种选项卡了解有关调查的更多信息。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>查看与调查相关的警报的详细信息

某些类型的警报会触发自动调查Microsoft 365。 若要了解更多信息，请参阅 [触发自动调查的警报策略](office-365-air.md#which-alert-policies-trigger-automated-investigations)。

1. 转到"Microsoft 365 Defender门户 () <https://security.microsoft.com> 并登录。
2. 在导航窗格中，选择操作 **中心**。
3. 在"挂起 **"或** " **历史记录"** 选项卡上，选择一个操作。 将打开其飞出窗格。
4. 在飞出窗格中，选择" **打开调查页面"**。
5. 选择 **"警报"** 选项卡以查看与该调查关联的所有警报的列表。
6. 选择列表中的某个项以打开其飞出窗格。 可以在那里查看有关警报详细信息。

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- 电子邮件计数在调查时计算，当您基于基础查询查询打开调查 (将重新计算某些) 。

- 为"电子邮件"选项卡上的电子邮件群集显示的电子邮件计数和群集飞出上显示的电子邮件数量值在调查时计算，并且不会更改。

- 电子邮件群集飞出控件的"电子邮件"选项卡底部显示的电子邮件计数和资源管理器中显示的电子邮件数反映了在调查初始分析后收到的电子邮件。

  因此，当调查分析阶段与管理员审查调查之间到达另外五封电子邮件时，显示原始数量为 10 封电子邮件的电子邮件群集将显示共 15 封电子邮件列表。 同样，旧调查可能开始显示比资源管理器查询显示更高的计数，因为 Microsoft Defender for Office 365 计划 2 的数据在试用的 7 天后和付费许可证的 30 天后过期。

  在不同的视图中同时显示计数历史计数和当前计数，以指示调查时的电子邮件影响以及直到运行修正之前的当前影响。

- 在电子邮件的上下文中，你可能会看到卷异常威胁图面作为调查的一部分。 与早期时间范围相比，卷异常指示调查事件时间周围类似电子邮件的峰值。 电子邮件流量峰值以及某些特征 (例如主题和发件人域、正文相似性以及发件人 IP) 是电子邮件活动或攻击的典型开始。 但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。

- 卷异常是一种潜在威胁，因此与使用防病毒引擎、爆炸或恶意信誉标识的恶意软件或网络钓鱼威胁相比，其严重程度可能更低。

- 不需要批准每个操作。 如果您不同意建议的操作，或者您的组织不选择某些类型的操作，您可以选择拒绝这些操作，或者只是忽略它们，不采取措施。

- 通过批准和/或拒绝所有操作，调查可以完全关闭 (状态) ，而保留某些操作未完成会导致调查状态变为部分修正状态。

## <a name="next-steps"></a>后续步骤

- [审阅和批准挂起的操作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
