---
title: 取消订阅
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: b1bc0bef-4608-4601-813a-cdd9f746709a
description: 了解如何取消 Office 365 for business 或 Microsoft 365 试用版或付费订阅。
ms.openlocfilehash: d3590f224757265af3107566023413d276443c46
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238250"
---
# <a name="cancel-your-subscription"></a>取消订阅

*资格：* 如果向用户分配的许可证数少于25个，则可以随时在管理中心中在线取消 Office 365 for business 试用版或付费订阅。 如果为用户分配了25个以上的许可证，请[致电支持部门以取消订阅](../../admin/contact-support-for-business-products.md)。

*退款：* 任何按比例贷项都将在下一个帐单周期内返回给您。

> [!NOTE]
> 如果您具有对同一产品的多个订阅（如 Office 365 企业版 E3），则取消其中一个将不会影响其他订阅中已购买的许可证或服务。

## <a name="steps-to-cancel-your-subscription"></a>取消订阅的步骤

如果您添加了自己的域名以与订阅一起使用，则必须在取消订阅之前删除该域。 有关详细信息，请参阅[从 Office 365 中删除域](../../admin/get-help-with-domains/remove-a-domain.md)。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品和服务</a>”页面。

2. 找到要取消的订阅，在 "**设置" & "操作**" 下，选择 "**取消订阅**"。

3. 查看重要日期，提供有关您要取消的原因的反馈，然后选择 "**取消订阅**"。

    你的订阅现在以**禁用**状态显示，并且在删除之前已缩减功能。 若要详细了解在已取消付费的 Office 365 for business 订阅时可预期的内容，请参阅[office 365 for business 订阅结束时对我的数据和访问有什么影响？](what-if-my-subscription-expires.md)

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>" 页。

2. 在 "**订阅**" 页上，选择订阅。

3. 从 "**其他操作**" 菜单中，选择 "**取消订阅**"。

    ![关闭 "更多操作" 菜单。](../../admin/media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)

4. 查看重要日期，提供有关您要取消的原因的反馈，然后选择 "**取消订阅**"。

    你的订阅现在以**禁用**状态显示，并且在删除之前已缩减功能。 若要详细了解在已取消付费的 Office 365 for business 订阅时可预期的内容，请参阅[office 365 for business 订阅结束时对我的数据和访问有什么影响？](what-if-my-subscription-expires.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>" 页。

2. 在 "**订阅**" 页上，选择订阅。

3. 从 "**其他操作**" 菜单中，选择 "**取消订阅**"。

    ![关闭 "更多操作" 菜单。](../../admin/media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)

4. 查看重要日期，提供有关您要取消的原因的反馈，然后选择 "**取消订阅**"。

    你的订阅现在以**禁用**状态显示，并且在删除之前已缩减功能。 若要详细了解在已取消付费的 Office 365 for business 订阅时可预期的内容，请参阅[office 365 for business 订阅结束时对我的数据和访问有什么影响？](what-if-my-subscription-expires.md)

::: moniker-end


## <a name="other-steps-you-might-have-to-take"></a>您可能需要执行的其他步骤

### <a name="change-custom-domain-settings"></a>更改自定义域设置

如果将自定义域与订阅一起使用，则必须执行一些额外的步骤，然后才能取消订阅。 如果没有自定义域，可以跳过前面以[保存数据](#save-your-data)。

#### <a name="change-your-domain-nameserver-records-if-needed"></a>更改您的域名称服务器记录（如果需要）

如果设置自定义域，则添加了 DNS 记录，以便域可与 Office 365 服务配合使用。 在删除您的域之前，请务必在 DNS 主机上更新 DNS 记录，如域 MX 记录。

例如，更改 DNS 主机上的 MX 记录。 发送到您的域的电子邮件将阻止进入您的 Office 365 地址，而是转到新的电子邮件提供商。 （MX 记录确定为您的域发送电子邮件的位置。）

- 如果您的 nameserver （NS）记录[指向 Office 365 名称服务器](../../admin/setup/add-domain.md)，则在您将 NS 记录更改为指向新的 DNS 主机（请参阅步骤2）之前，对 MX 记录所做的更改不会生效。

- 在更新 MX 记录之前，让您的用户知道您计划切换其电子邮件的日期，以及您计划使用的新电子邮件提供商。 此外，如果您的用户要将其现有的 Office 365 电子邮件移动到新的提供商，他们必须执行额外的步骤。

- 在你更改 MX 记录时，请遵照本文中的其余步骤。

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>更新您的域 MX 和其他 DNS 记录（如果使用的是自定义域）

如果您在设置域时将您的 nameserver （NS）记录切换到 Office 365，则必须在您计划使用的 DNS 主机上设置或更新 MX 记录和其他 DNS 记录，然后将您的 NS 记录更改为该 DNS 主机。

如果您在设置域时没有切换 NS 记录，则当您更改 MX 记录时，您的邮件会立即开始转到新的地址。

有关详细信息，请参阅[Office 365 如何管理我的 DNS 记录？](../../admin/setup/domains-faq.md#how-does-office-365-manage-my-dns-records)。 若要更改 NS 记录，请参阅[从 Office 365 删除域](../../admin/get-help-with-domains/remove-a-domain.md)。

### <a name="save-your-data"></a>保存数据

当取消生效时，您的用户将失去对其数据的访问权限。 在取消订阅之前，让他们将其 OneDrive for Business 或 SharePoint Online 文件保存到另一个位置。 您留下的任何客户数据在30天后可能会被删除，并且在取消后的180天内被删除。

- 若要将电子邮件、联系人、任务和日历信息移动到另一个帐户，请参阅[将电子邮件、联系人和日历导出或备份到 Outlook .pst 文件](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)。

- 要将 SharePoint Online 环境（OneDrive for Business 或团队网站）中的文档库或列表内容（如联系人）保存到文件共享或本地计算机，请参阅[手动迁移 SharePoint Online 内容](https://support.microsoft.com/kb/2783484)。

### <a name="uninstall-office-optional"></a>卸载 Office （可选）

如果取消了你的订阅，但未将用户移动到包含 Office 的其他订阅，Office 365 将在缩减功能模式下运行。 当发生这种情况时，用户只能读取和打印文档，Office 365 应用程序将显示未[授权的产品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。 若要避免任何混淆，请要求用户卸载计算机上的 [Office](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)。

## <a name="related-articles"></a>相关文章

[续订订阅](renew-your-subscription.md)

[重新激活订阅](reactivate-your-subscription.md)

[切换到其他计划或订阅](switch-to-a-different-plan.md)
