---
title: 用于 Microsoft 365 的 Exchange Online 监视
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 使用 Exchange Online 监视获取有关 Microsoft 365 中电子邮件事件或通报信息。
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286437"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>用于 Microsoft 365 的 Exchange Online 监视

可使用 Microsoft 365 管理中心中的 Exchange Online 监视来监视组织的 Microsoft 365 订阅的 Exchange 服务运行状况。 Exchange Online 监视提供了有关在以下类别中收集的事件和通报的信息：

- **基础结构**：在 Microsoft 所拥有的用于提供定期更新和解决问题的 Microsoft 365 基础结构中检测到了问题。 例如，由于 Exchange 或其他 Microsoft 365 云基础结构的问题，用户无法访问 Exchange Online。
- **第三方基础结构**：在组织已取得相关性的第三方基础结构中检测到问题，并需要组织提供的措施来解决问题。 例如，用户身份验证事务受到阻止用户连接到 Exchange Online 的第三方安全令牌服务 (STS) 提供程序的限制。
- **客户基础结构**：在组织基础结构中检测到问题，并要求组织执行操作以解决问题。 例如，用户无法访问 Exchange Online，因为证书已过期，他们无法获取由组织托管的 STS 提供商提供的身份验证令牌。

以下为 Microsoft 365 管理中心中的 **服务运行状况** 页面的示例， 可通过 **“运行状况” > “服务运行状况”** 查看。

![Microsoft 365 管理中心中的“服务运行状况”页面](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

**状态** 列的值表示服务状态是否正常，或基于 Microsoft 维护的云服务是否存在建议或事件。 

**你的组织和第三方问题** 的值表示你的组织基础结构或第三方软件通过 Exchange Online 对用户的服务运行状况体验的影响。 建议或事件需要 *你的* 操作才能解决。

下面是 Microsoft 365 管理中心中的 **Exchange Online** 监视页面的示例， 可通过 **“运行状况” > “服务运行状况” > “Exchange Online”** 查看。

![Microsoft 365 管理中心中的 Exchange Online 监视页面](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

使用 **Exchange Online** 监视页面，可查看 Exchange Online 服务是否运行正常，以及是否存在任何关联的事件或通报。 借助 Exchange Online 监视，可查看特定电子邮件方案的服务运行状况，查看准实时信号，确定方案产生的影响。 

## <a name="requirements"></a>要求

对于满足这些要求的客户，将启用此预览版： 

- 你的组织需要从以下产品之一或其组合中获取至少 5,000 的许可证计数：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 

  例如，你的组织可以具有 3,000 个 Office 365 E3 许可证，2,500 个 Microsoft 365 E5，即总计拥有 5,500 个合格产品许可证。

- 你的组织需要拥有至少50 个 Exchange Online 月活跃用户。

借助 Exchange 监视，可基于电子邮件阅读活动查看以下电子邮件客户端的运行状况：

- Outlook 桌面版
- Web 上的 Outlook
- iOS 版和 Android 版的本机邮件客户端 
- 用于 iOS 和 Android 的 Outlook 移动应用 
- Outlook Mac 客户端

通过这些客户端，你可以根据阅读电子邮件的用户以及仪表板中的事件数和建议，查看最近 30 分钟内的活动用户数。 此数据将与前一周的相同间隔进行比较，以查看是否存在问题。 

>[!Note]
> 活跃用户计数由单个活动测量，例如，用户阅读电子邮件。 该帐户仅适用于最近 30 分钟的活动。
>

你也可以在以下情况下监视 Exchange 运行状况：

- **邮件流**：邮件连接到 Microsoft 365 网络后，在不延迟的情况下成功传送到邮箱的邮件数。 
- **基本身份验证和新式验证**：Exchange Online 服务中成功验证的用户数。

![用于在邮件传递中监视 Exchange 运行状况的示例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

在所有这些情况下，获得的是主仪表板中的最后 30 分钟的关键数量。 上述每种情况的详细视图将显示与前一周相比，在 30 分钟聚合的情况下，七天内的准实时趋势。 

## <a name="send-us-feedback"></a>向我们发送反馈

可以通过下列两种方式提供反馈：

- 使用 **“提供反馈”** 选项，可在 Microsoft 365 管理中心的每个页面上提供反馈。
- 使用 **这篇文章是否有用？** 链接提交特定事件或通报的反馈。

![这篇文章是否有用？ 链接提交特定事件或通报的反馈](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>常见问题解答

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. 为什么在 Microsoft 365 管理中心中的“运行状况”下看不到“Exchange Online 监视”？ 

首先，请确保已在 Microsoft 365 管理中心 **主页** 页面上启用了新管理中心。 

然后，请确保满足以下两项要求： 

- 你的组织需要从以下产品之一或其组合中获取至少 5,000 的许可证计数：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 
- 你的组织需要具有至少50 个 Exchange Online 月活跃用户。

如果组织的许可证计数低于 5,000 个用户，且月活跃用户低于 50，则在满足这些要求之前，将不会启用 Exchange Online 监视。

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. 仪表板中每个客户端的活动用户账户计数似乎很低。 向用户分配了大量活动的许可证。 这意味着什么？ 

监视中显示的活跃用户计数是基于 30 分钟的窗口，其中用户执行了功能中调用的活动。 这不应该与使用数字相混淆。 若要查看使用数字，请使用 Microsoft 365 管理中心中的活动报告（**“报告” > “使用情况”**）。

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. 其他服务（如 Teams 和 SharePoint）是否有其他监视方案？ 

Microsoft 在 Microsoft 365 管理中心中的服务运行状况仪表板内直接集成了这种体验。 这将使 Microsoft 有机会扩展其他服务的监视方案，在有新闻可供共享时，将通知这些情况。 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. 此体验的总体可用性计划是什么？ 

Microsoft 已直接在 Microsoft 365 管理中心中的 **服务运行状况** 仪表板上集成了 Exchange Online 监视。 

通过这项全新的集成体验，Microsoft 计划收集你的反馈，然后定义我们的总体可用性计划。

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. 这是免费的（含）还是付费的（额外）功能？ 

此功能适用于公共预览版，并且仅适用于满足问题 1 的要求的客户。

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. 如何提供反馈？ 

有关一般反馈，请使用 **Exchange Online** 监视页右下角的 **提供反馈** 图标。 

有关事件或通报的反馈，请使用 **这篇文章是否有用？** 链接。

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. 在哪里处理这些用于显示活动趋势的方案的数据？

数据在 Exchange Online 服务中进行处理。如果在请求到达 Exchange Online 之前出现错误，或 Exchange Online 出现错误，将会看到活动信号下降。
