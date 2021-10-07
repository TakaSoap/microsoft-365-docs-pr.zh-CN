---
title: 攻击模拟培训部署注意事项和常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解部署注意事项和有关攻击模拟和 Microsoft Defender for Microsoft 365 E5 计划 2 Office 365培训的常见问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 19b8997a5f2d1f8df40c740fb996432b13a21d3b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196593"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>攻击模拟培训部署注意事项和常见问题解答

攻击模拟培训现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)。 攻击模拟培训使 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织可以度量和管理社交工程风险，通过允许创建和管理由实际、已取消武器化网络钓鱼负载的网络钓鱼模拟。 与 Terranova 安全性合作提供的超目标培训可帮助提高知识并改变员工行为。

有关攻击模拟培训入门的信息，请参阅使用 [攻击模拟培训入门](attack-simulation-training-get-started.md)。

尽管整个模拟创建和计划体验设计为可自由流动且流畅，但企业规模运行的模拟通常需要进行规划。 本文有助于解决客户在其自己的环境中运行模拟时所看到的特定挑战。

## <a name="issues-with-end-user-experiences"></a>最终用户体验问题

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Google 网页浏览阻止的网络钓鱼保险箱 URL

URL 信誉服务可能会将攻击模拟培训使用的一个或多个 URL 标识为不安全。 Google 保险箱 Chrome 中的浏览功能会阻止一些带有欺骗性网站提前消息的模拟网络钓鱼 **URL。** 虽然我们与许多 URL 信誉供应商合作，始终允许我们的模拟 URL，但并不总是具有完全覆盖。

![Google Chrome 中的欺骗性网站提前警告。](../../media/attack-sim-chrome-deceptive-site-message.png)

请注意，此问题不会影响Microsoft Edge。

作为规划阶段的一部分，请务必先检查 URL 在支持的 Web 浏览器中的可用性，然后再在网络钓鱼活动中使用该 URL。 如果 Google 保险箱阻止 URL，请按照 Google 的本指南[](https://support.google.com/chrome/a/answer/7532419)允许访问 URL。

有关 [攻击模拟培训当前](attack-simulation-training-get-started.md) 使用的 URL 列表，请参阅使用攻击模拟培训入门。

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>网络代理解决方案和筛选器驱动程序阻止的网络钓鱼模拟和管理 URL

您的中间安全设备或筛选器可能会阻止或删除网络钓鱼模拟 URL 和管理 URL。 例如：

- 防火墙
- WAF 解决方案 (Web) 防火墙
- 例如，第三方筛选器 (，例如内核模式) 

尽管我们看到此层中很少客户被阻止，但确实如此。 如果遇到问题，请考虑将以下 URL 配置为绕过安全设备或筛选器所需的扫描：

- 如使用攻击模拟培训入门中所述的模拟[网络钓鱼 URL。](attack-simulation-training-get-started.md)
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>未向所有目标用户传递模拟消息

实际接收模拟电子邮件的用户数可能小于模拟的目标用户数。 作为目标验证的一部分，将排除以下类型的用户：

- 收件人电子邮件地址无效。
- 来宾用户。
- 在 Azure AD Azure Active Directory (中不再) 。

只有具有有效邮箱的有效非来宾用户才包括在模拟中。 如果使用通讯组或启用邮件的安全组作为目标用户，可以使用[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的[Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet 查看和验证通讯组成员。

## <a name="issues-with-attack-simulation-training-reporting"></a>攻击模拟培训报告问题

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>攻击模拟培训报告不包含任何活动详细信息

攻击模拟培训附带丰富、可操作见解，可让你了解员工的威胁就绪进度。 如果攻击模拟培训报告未填充数据，请验证审核日志搜索是否在你的组织中打开 (默认情况下是否) 。

攻击模拟培训需要审核日志搜索，以便可以捕获、记录和重新读取事件。 关闭审核日志搜索对攻击模拟培训有以下后果：

- 报告数据并非在所有报告中都可用。 报告将显示为空。
- 由于数据不可用，因此将阻止培训作业。

若要打开搜索审核日志，请参阅打开 [审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

> [!NOTE]
> 未向用户分配 E5 许可证也导致了空活动详细信息。 确认至少向活动用户分配了一个 E5 许可证，以确保捕获并记录报告事件。

### <a name="simulation-reports-are-not-updated-immediately"></a>模拟报告不会立即更新

详细的模拟报告不会在启动市场活动后立即更新。 不要担心;此行为是预期行为。

每个模拟活动都有一个生命周期。 首次创建时，模拟将位于 **计划** 状态。 模拟开始时，它将转换为 **正在进行状态。** 完成后，模拟将转换为 **"已完成"** 状态。

当模拟状态为 **计划** 时，模拟报告将大部分为空。 在此阶段，模拟引擎将解析目标用户电子邮件地址、展开通讯组、从列表中删除来宾用户等：

![在计划状态中报告。](../../media/attack-sim-empty-reporting.png)

模拟进入正在进行阶段 **后** ，你将注意到信息开始欺骗报告：

![报告状态为"正在进行"。](../../media/attack-sim-in-progress.png)

在过渡到"正在进行"状态后，可能需要 30 分钟才能更新单个 **模拟** 报告。 报告数据将继续生成，直到模拟达到 **"已完成"** 状态。 报告更新将按照以下间隔发生：

- 前 60 分钟每 10 分钟。
- 每隔 15 分钟，60 分钟到 2 天。
- 每隔 2 天到 7 天每 30 分钟。
- 每 7 天 60 分钟。

"概述 **"页上** 的小部件提供了组织基于模拟的安全状态在一段时间的快速快照。 由于这些小组件反映了整体安全状况和一段时间的旅程，因此在每个模拟市场活动完成后会更新它们。

> [!NOTE]
> 可以使用各种报告 **页面上** 的"导出"选项提取数据。

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>用户报告为网络钓鱼的邮件不会显示在模拟报告中

攻击模拟器培训中的模拟报告提供有关用户活动的详细信息。 例如：

- 单击邮件中链接的用户。
- 放弃其凭据的用户。
- 将邮件报告为网络钓鱼的用户。

如果用户报告为网络钓鱼的邮件未在攻击模拟培训模拟报告中捕获，则可能有一个 Exchange 邮件流规则 (也称为传输规则) 该规则阻止向 Microsoft 传递报告的邮件。 验证任何邮件流规则是否未阻止到以下电子邮件地址的传递：

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- not \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>其他常见问题

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>问：对于模拟活动，建议采用什么方法面向用户？

答：目标用户可以使用以下几种选项：

- 包括当前 (用户数少于 40，000 的组织) 。
- 选择特定用户。
- 从 CSV 文件选择用户 (每行一) 。
- 基于 Azure AD 组的定位。

我们发现通过 Azure AD 组标识目标用户的市场活动通常更易于管理。

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>问：从 CSV 导入或添加用户时，目标用户是否有限制？

答：从 CSV 文件导入收件人或向模拟中添加单个收件人的限制为 40，000。

收件人可以是单个用户或组。 由于一个组可能包含数百个或数千个收件人，因此不会对单个用户的数量设置实际限制。

管理大型 CSV 文件或添加多个单个收件人可能很麻烦。 使用 Azure AD 组将简化模拟的总体管理。

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>问：Microsoft 是否提供其他语言的负载？

答：目前，有 5 个本地化有效负载可用。 我们已注意到，现有有效负载到其他语言的任何直接或机器翻译都会导致不准确和相关性降低。

也就是说，可以使用自定义有效负载创作体验，以你选择的语言创建自己的有效负载。 我们还强烈建议你获取用于面向特定地理位置的用户的现有有效负载。 换句话说，让攻击者本地化内容。

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>问：如何切换到其他语言以用于我的管理门户和培训体验？

答：在Microsoft 365或Office 365中，语言配置是特定于每个用户帐户的集中式配置。 有关如何更改语言设置的说明，请参阅更改 Microsoft 365 for Business 中的显示语言[和时区](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)。

请注意，配置更改可能需要 30 分钟才能在所有服务之间同步。

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>问：能否触发测试模拟，了解在启动功能齐全的市场活动之前它的外观？

答：可以！ 在 **向导中用于** 创建新模拟的最后一个"审阅模拟"页上，有一个 **"发送测试"选项**。 此选项将向当前登录的用户发送示例网络钓鱼模拟消息。 验证收件箱中的网络钓鱼邮件后，可以提交模拟。

![在"审阅模拟"页上发送测试按钮。](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>问：我能否将属于不同租户的用户作为同一模拟市场活动的一部分？

答：否。 目前不支持跨租户模拟。 验证所有目标用户是否位于同一租户中。 任何跨租户用户或来宾用户都将从模拟市场活动中排除。

### <a name="q-how-does-region-aware-delivery-work"></a>问：区域感知传递如何工作？

答：区域感知传递使用目标用户邮箱的 TimeZone 属性和"not before"逻辑来确定何时传递邮件。 例如，请考虑以下方案：

- 在太平洋时区 (UTC-8) 的上午 7：00，管理员创建并计划一个活动，以在当天上午 9：00 开始。
- UserA 位于东部时区， (UTC-5) 。
- UserB 也位于太平洋时区。

同一天上午 9：00，模拟消息将发送到 UserB。 使用区域感知传递，邮件不会在同一天发送给 UserA，因为太平洋时间上午 9：00 是东部时间晚上 12：00。 相反，邮件会于第二天东部时间上午 9：00 发送到 UserA。

因此，在启用了区域感知传递的市场活动的初始运行中，模拟消息可能只发送给特定时区的用户。 但是，随着时间的推移，越来越多的用户进入作用域，目标用户将会增加。