---
title: 管理许可证请求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: 了解如何查看和批准或拒绝来自适用于 Microsoft 365 for business 订阅的用户的许可证请求。
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597648"
---
# <a name="manage-license-requests"></a>管理许可证请求

> [!NOTE]
> 本文中的信息仅适用于自助服务购买的产品。 若要了解详细信息，请参阅[自助式购买常见问题解答](../subscriptions/self-service-purchase-faq.md)。

如果您在组织中禁用了自助式购买，则可以使用许可证请求来管理用户的许可证请求流程。 当用户尝试为已阻止的产品进行自助服务购买时，他们可以向管理员提交许可证请求。在发出请求时，他们可以添加还需要产品许可证的其他用户的姓名。

> [!NOTE]
> 如果阻止用户进行自助购买，Microsoft 不会向其发送营销电子邮件。 此外，如果他们使用的是试用版产品，他们将不会看到要购买的提示。 若要了解详细信息，请参阅[管理自助购买 (管理员) ](../subscriptions/manage-self-service-purchases-admins.md)。

若要查看和管理许可证请求，管理员使用 "**许可**" 页面上的 "**请求**" 选项卡。 该列表显示所请求的产品的名称、请求许可证的人员的姓名、请求的日期以及请求的状态。 管理员可以筛选列表以显示挂起或已完成的请求。 请求保留30天。

## <a name="before-you-begin"></a>准备工作

若要执行本文中的任务，您必须是全局管理员。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-your-own-request-process"></a>使用您自己的请求过程

如果您的组织有自己的请求过程，则可以改为使用它。 创建一个在用户请求许可证时向其显示的消息。

> [!IMPORTANT]
> 如果您使用自己的请求过程，则 "**请求**" 选项卡上将不会显示任何请求。在您添加邮件之前，现有请求将一直显示，直到您批准或拒绝它们为止。

1. 在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。
2. 选择 "**使用现有的请求过程**"。
3. 在右侧窗格中的 "**消息**" 框中，键入您希望用户在请求许可证时看到的消息。 如果要同时包含指向组织策略或其他文档的链接，请在 "**指向文档的链接" (可选) ** "文本框中输入 URL。
4. 选择“**保存**”。

当您返回 "**请求**" 列表时，您会看到您**使用的是自己的许可证请求过程**的消息。 若要对发送给用户的邮件进行更改，请选择 "**使用现有请求过程**"。

## <a name="stop-using-your-own-request-process"></a>停止使用自己的请求过程

1. 在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。
2. 选择 "**使用现有的请求过程**"。
3. 在右窗格中，清除 "**使用我的组织的请求过程**" 复选框。
4. 选择“**保存**”。

## <a name="approve-or-deny-a-license-request"></a>批准或拒绝许可证请求

1. 在管理中心中，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面，然后选择 "**请求**" 选项卡。
2. 选择包含您要查看的请求的行。 右窗格显示有关用户需要许可证的产品的详细信息。
3. 若要拒绝整个请求，请选择 "**不批准**"，并在对话框中，选择 "**不批准**"。
4. 若要为请求拒绝某些用户，但要批准其他用户，请按要删除的用户的名称选择 X。 它们的名称在不**分配给这些用户**的情况下被移动。
5. 如果您有多个产品，请在 "**选择产品**" 下，选择要用于为其分配许可证的产品。
6. 若要拒绝用户访问某些应用和服务，请展开 **"打开或关闭应用程序和服务**"，然后清除要排除的应用和服务的复选框。
7. 在窗格底部的文本框中，键入可选消息。
8. 完成后，选择 "**批准**"。 右窗格显示请求的详细信息。
9. 关闭右窗格。
    用户收到一封电子邮件，告知其请求已被批准或拒绝。

## <a name="related-content"></a>相关内容

[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md) (文章) \
[将用户移动到其他订阅](../subscriptions/move-users-different-subscription.md) (文章) \
 (文章) [购买或删除订阅许可证](buy-licenses.md)