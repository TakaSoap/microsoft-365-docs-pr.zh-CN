---
title: 取消订阅
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
- AdminSurgePortfolio
- commerce_subscriptions
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 了解如何在 Microsoft 365 管理中心中取消 Dynamics 365、Intune、Power Platform 和 Microsoft 365 商业试用版或付费订阅。
ms.date: 01/20/2022
ms.openlocfilehash: f1c64090117a93d33ccf69222cbe0b7f7d06a88e
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156168"
---
# <a name="cancel-your-subscription"></a>取消订阅

你可以随时在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 356 管理中心</a> 中取消订阅。 但是，如果要获得退款，则必须满足某些退款资格要求。 有关详细信息，请参阅 [了解退款资格](#understand-refund-eligibility)。

如果对同一产品（例如 Microsoft 365 商业高级版）有多个订阅，则取消一个订阅不会影响其他订阅内已购买的许可证或服务。

> [!IMPORTANT]
> 本文仅适用于 Dynamics 365、Intune、Power Platform 和 Microsoft 365 商业版订阅。 如果你有 Microsoft 365 家庭版或个人版，请参阅 [取消 Microsoft 365 订阅](https://support.microsoft.com/office/cancel-a-microsoft-365-subscription-46e2634c-c64b-4c65-94b9-2cc9c960e91b?OCID=M365_DocsCancel_Link)。

## <a name="before-you-begin"></a>开始之前

你必须是全局管理员或帐单管理员才能执行本文中的任务。有关详细信息，请参阅“[关于管理员角色](../../admin/add-users/about-admin-roles.md)”。

## <a name="understand-refund-eligibility"></a>了解退款资格

### <a name="if-you-have-a-billing-profile"></a>如果你有计费对象信息

你必须在启动付费订阅后 72 小时内取消，才能按比例获得已支付的未使用时间退款。 退款在 72 小时后不可用。

例如，假设你购买了一年期订阅，并按单个许可证每个月支付 20 美元。 你于 2022 年 2 月 1 日上午 11 点购买了订阅，并决定在 2022 年 2 月 3 日上午 11 点取消订阅。 我们为你持有订阅的两天扣除 1.43 美元，你将获得 18.57 美元的按比例退款。

**不确定你是否有计费对象信息？** 要了解如何查找你是否有计费对象信息，请参阅 [查看我的计费对象信息](../billing-and-payments/manage-billing-profiles.md#view-my-billing-profiles)。

### <a name="if-you-dont-have-a-billing-profile"></a>如果没有计费对象信息

则可以使用下表来帮助确定是否可以自行取消订阅。

|如果你的订阅有  |则可以  |
|--------------|--------------|
|25 个或更少的许可证  | 随时在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 356 管理中心</a> 中在线取消试用版或付费订阅。        |
|超过 25 个许可证   | 请将许可证数量减少到 25 个或更少，然后重试，或 [呼叫支持人员以取消订阅](../../admin/get-help-support.md)。        |

如果订阅没有计费对象信息，则只能在购买或续订订阅后的有限时间段内取消。 如果取消时段已过，请在订阅期限结束时 [禁用定期计费](renew-your-subscription.md) 以取消订阅。

如果在有限时间段内取消，则在下一个计费周期内，将向你返还任何按比例计算的额度。

## <a name="steps-to-cancel-your-subscription"></a>取消订阅的步骤

如果你之前添加了自己的域名以用于订阅，则必须在取消订阅前删除此域。有关详细信息，请参阅[删除域](../../admin/get-help-with-domains/remove-a-domain.md)。

::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">你的产品</a>”页面。

::: moniker-end

2. 找到要取消的订阅。选择三个点（更多操作），然后选择“**取消订阅**”。

3. 在“**取消订阅**”窗格中，选择取消原因。可选择提供任何反馈。

4. 选择“**保存**”。

你的订阅现将显示为“**已禁用**”状态，且将在删除之前使用缩减功能。若要深入了解在取消已付费的 Microsoft 365 商业版订阅后会发生什么情况，请参阅 [我的 Microsoft 365 商业版订阅结束后对我的数据和访问权限有何影响？](what-if-my-subscription-expires.md)

> [!NOTE]
> 如果显式删除订阅，则它将跳过过期和禁用阶段，而且会立即删除 SharePoint Online 数据和内容（包括 OneDrive）。

## <a name="what-happens-when-you-cancel-a-subscription"></a>取消订阅会发生什么？

如果在期限结束之前取消订阅，订阅状态将直接进入禁用状态。 在大多数国家和地区，大多数订阅的禁用状态会持续 90 天。 订阅处于禁用状态时，管理员仍然可以访问和备份其组织的数据，但我们建议管理员在取消订阅之前[备份其数据](back-up-data-before-switching-plans.md)，尤其是在该订阅是其唯一订阅的情况下。 管理员也可以在订阅处于禁用状态时重新激活订阅。

90 天后，订阅进入已删除状态。 将会在取消订阅的 90 天之后、180 天之前删除遗留的任何数据。 在取消订阅达到已删除状态之前，无法删除已取消订阅的付款方式。

### <a name="what-to-expect-for-you-and-your-users-if-you-cancel-a-subscription"></a>取消订阅对你和你的用户的影响。
  
- **管理员访问权限** 管理员仍可登录和访问管理中心，并根据需要购买其他订阅。 作为全局管理员或账单管理员，你有 90 天时间可以 [重新激活订阅](reactivate-your-subscription.md) 且保留所有数据。

- **用户访问权限** 你的用户将不能使用 OneDrive for Business 等服务，也不能访问客户数据，例如团队网站上的电子邮件或文档。 Office 应用程序（如 Word 和 Excel）最终将进入只读且缩减功能模式，并显示 [未经授权的产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。

要了解详细信息，请参阅 [我的订阅结束后对我的数据和访问权限有何影响？](what-if-my-subscription-expires.md)

> [!IMPORTANT]
> 如果希望在典型的禁用期结束之前删除订阅数据，可以 [关闭帐户](../close-your-account.md)。

## <a name="other-steps-you-might-have-to-take"></a>其他可能必须执行的步骤

### <a name="change-custom-domain-settings"></a>更改自定义域设置

如果对订阅使用自定义域，则在可以取消订阅之前，必须执行一些额外步骤才可取消订阅。 如果没有自定义域，可跳到“[保存数据](#save-your-data)。

#### <a name="change-your-domain-nameserver-records-if-needed"></a>更改域名服务器记录（若需要）

如果设置了自定义域，则添加 DNS 记录以便此域使用 Microsoft 365 服务。在删除域之前，请确保在 DNS 主机上更新 DNS 记录，如域的 MX 记录。

例如，在 DNS 主机上更改 MX 记录。发送到你的域的电子邮件不再发到你的 Microsoft 地址，转而发到新的电子邮件提供商。（MX 记录确定针对你的域的电子邮件发送到何处。）

- 如果名称服务器 (NS) 记录 [当前指向 Office 365 名称服务器](../../admin/setup/add-domain.md)，则仅在更改 NS 记录以指向新的 DNS 主机（参见步骤 2）后，对 MX 记录的更改才会生效。

- 在更新 MX 记录之前，请告知用户你要切换其电子邮件的日期，以及计划使用的新电子邮件提供商。 此外，如果用户想要将其现有 Microsoft 电子邮件移动到新的提供商，他们必须执行额外的步骤。

- 在你更改 MX 记录当天，请执行本文中的其余步骤。

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>更新域的 MX 或其他 DNS 记录（如果正在使用自定义域）

如果你在设置域时将名称服务器 (NS) 记录切换为 Microsoft 365，则必须在计划使用的 DNS 主机处设置或更新 MX 记录和其他 DNS 记录，然后将 NS 记录更改到该 DNS 主机。

如果在设置域时未切换 NS 记录，则更改 MX 记录后，邮件将立即开始转到新的地址。

要更改 NS 记录，请参阅 [删除域](../../admin/get-help-with-domains/remove-a-domain.md)。

### <a name="save-your-data"></a>保存数据

取消生效后，你的用户将失去对其数据的访问权限。取消订阅前，请让他们将其 OneDrive for Business 或 SharePoint Online 文件保存到其他位置。将会在取消订阅的 30 天之后、180 天之前删除遗留的任何客户数据。

- 若要将电子邮件、联系人、任务和日历信息移动到另一个帐户，请参阅[将电子邮件、联系人和日历导出或备份到 Outlook .pst 文件](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)。

- 要将 SharePoint Online 环境（OneDrive for Business 或团队网站）中的文档库或列表内容（如联系人）保存到文件共享或本地计算机，请参阅[手动迁移 SharePoint Online 内容](/sharepoint/troubleshoot/migration-tool/content-manual-migration)。

### <a name="uninstall-office-optional"></a>卸载 Office（可选）

如果已取消订阅且未 [将用户移动到不同订阅](move-users-different-subscription.md)（包括 Microsoft 365），则 Microsoft 365 会以缩减功能模式运行。 此情况发生时，用户只能阅读和打印文档，并且 Microsoft 365 应用程序显示 [未经授权产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。 要避免任何混淆，请让你的用户从其计算机上 [卸载 Office](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)。

## <a name="next-steps"></a>后续步骤

若要完全关闭 Microsoft 帐户，请参阅 [关闭帐户](../close-your-account.md)。

## <a name="related-content"></a>相关内容

[续订订阅](renew-your-subscription.md)（文章）。
[重新激活订阅](reactivate-your-subscription.md)（文章）
[将用户移动到其他订阅](move-users-different-subscription.md)（文章）
