---
title: 取消订阅
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 了解如何在 Microsoft 365 管理中心中取消 Dynamics 365、Intune、Power Platform 和 Microsoft 365 商业试用版或付费订阅。
ms.date: 03/31/2022
ms.openlocfilehash: d6b6c078c5f0d1b44143f3a9cc2d336a0a80fe03
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595271"
---
# <a name="cancel-your-subscription"></a>取消订阅

如果要取消订阅，最简单的方法是[关闭定期计费](renew-your-subscription.md)。 关闭定期计费后，可以继续使用订阅，直到订阅期限到期为止。 如果要立即取消，请使用本文中的信息和步骤执行此操作。

> [!IMPORTANT]
> 本文仅适用于 Dynamics 365、Intune、Power Platform 和 Microsoft 365 商业版订阅。 如果你有 Microsoft 365 家庭版或个人版，请参阅 [取消 Microsoft 365 订阅](https://support.microsoft.com/office/cancel-a-microsoft-365-subscription-46e2634c-c64b-4c65-94b9-2cc9c960e91b?OCID=M365_DocsCancel_Link)。

## <a name="before-you-begin"></a>开始之前

- 你必须是全局管理员或帐单管理员才能执行本文中的任务。有关详细信息，请参阅“[关于管理员角色](../../admin/add-users/about-admin-roles.md)”。
- 在取消订阅之前，请确保用户 [保存其数据](#save-your-data)。
- 如果之前添加了自己的域名来使用订阅，则必须在取消订阅之前 [删除该域](../../admin/get-help-with-domains/remove-a-domain.md)。
- 如果你有域订阅，若要阻止该订阅的其他任何费用， [请关闭定期计费](renew-your-subscription.md)。

## <a name="determine-your-cancellation-options"></a>确定取消选项

> [!IMPORTANT]
> 在继续之前，[请确定你是否具有计费对象信息](../billing-and-payments/manage-billing-profiles.md#view-my-billing-profiles)。

### <a name="if-you-have-a-billing-profile"></a>如果你有计费对象信息

如果你在订阅开始或续订后七天内取消，则只能取消并收到按比例计算的信用额度或退款。 如果在此有限时段内取消，按比例计算的信用额度将计入下一张发票，或在下一个计费周期中退款给你。

如果需要在订阅开始或续订后七天内取消，请转到本文稍后介绍的 [取消订阅步骤](#steps-to-cancel-your-subscription)。

如果超过七天，则 [禁用定期计费](renew-your-subscription.md)。此设置可防止再次向你收取订阅费用，并允许你在订阅的剩余时间内继续访问你的产品和服务。

### <a name="if-you-dont-have-a-billing-profile"></a>如果没有计费对象信息

如果在开始或续订订阅后取消，则会收到按比例计算的信用额度或退款。 信用额度将计入你的下一张发票，或在下一个计费周期中退款给你。

取消试用版或付费订阅的步骤取决于订阅中的许可证数量。 下表介绍了根据许可证数量可以执行的步骤。

|如果你的订阅有  |则可以  |
|--------------|--------------|
|25 个或更少的许可证  | 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中[使用以下步骤以在线取消](#steps-to-cancel-your-subscription)你的试用版或付费订阅。        |
|超过 25 个许可证   | 将许可证数量减少为 25 个或更少，然后 [使用以下步骤取消](#steps-to-cancel-your-subscription)。      |

如果无法减少许可证数量，则 [禁用定期计费](renew-your-subscription.md)。此设置可防止再次向你收取订阅费用，并允许你在订阅的剩余时间内继续访问你的产品和服务。

如果无法取消订阅，请[联系客户服务](../../admin/get-help-support.md)寻求帮助。

## <a name="steps-to-cancel-your-subscription"></a>取消订阅的步骤

> [!NOTE]
> 如果对同一产品（例如 Microsoft 365 商业高级版）有多个订阅，则取消一个订阅不会影响其他订阅内已购买的许可证或服务。

::: moniker range="o365-worldwide"

1. 在 Microsoft 365 管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">你的产品</a>”页面。

::: moniker-end

2. 找到要取消的订阅。选择三个点（更多操作），然后选择“**取消订阅**”。

3. 在“**取消订阅**”窗格中，选择取消原因。可选择提供任何反馈。

4. 选择“**保存**”。

你的订阅现将显示为“**已禁用**”状态，且将在删除之前使用缩减功能。若要深入了解在取消已付费的 Microsoft 365 商业版订阅后会发生什么情况，请参阅 [我的 Microsoft 365 商业版订阅结束后对我的数据和访问权限有何影响？](what-if-my-subscription-expires.md)

> [!IMPORTANT]
> 如果显式删除订阅，则会跳过 **过期** 和 **禁用** 状态，而且会立即删除 SharePoint Online 数据和内容（包括 OneDrive）。

## <a name="save-your-data"></a>保存数据

取消生效后，你的用户将失去对其数据的访问权限。取消订阅前，请让他们将其 OneDrive for Business 或 SharePoint Online 文件保存到其他位置。将会在取消订阅的 30 天之后、180 天之前删除遗留的任何客户数据。

- 若要将电子邮件、联系人、任务和日历信息移动到另一个帐户，请参阅[将电子邮件、联系人和日历导出或备份到 Outlook .pst 文件](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)。
- 要将 SharePoint Online 环境（OneDrive for Business 或团队网站）中的文档库或列表内容（如联系人）保存到文件共享或本地计算机，请参阅[有关手动迁移 SharePoint Online 内容的信息](/sharepoint/troubleshoot/migration-tool/content-manual-migration)。

## <a name="next-steps"></a>后续步骤

### <a name="uninstall-office-optional"></a>卸载 Office（可选）

如果已取消订阅，但未[将用户移动到其他包括 Microsoft 365 的订阅](move-users-different-subscription.md)，Microsoft 365 将以缩减功能模式运行。发生此情况时，用户仅可阅读和打印文档，且 Microsoft 365 应用程序将显示[未经授权产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。若要避免任何混淆，请要求用户[卸载计算机上的 Office](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)。

### <a name="close-your-account-optional"></a>关闭你的帐户(可选)

若要完全关闭 Microsoft 帐户，请参阅 [关闭帐户](../close-your-account.md)。

## <a name="related-content"></a>相关内容

[续订订阅](renew-your-subscription.md)（文章）。
[重新激活订阅](reactivate-your-subscription.md)（文章）
[将用户移动到其他订阅](move-users-different-subscription.md)（文章）
