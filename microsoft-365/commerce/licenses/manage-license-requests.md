---
title: 管理许可证请求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: 了解如何查看和批准或拒绝用户针对企业版订阅Microsoft 365请求。
ms.date: 06/07/2021
ms.openlocfilehash: 3a1290c071fa96be654e645d6f7ca82197ecc4b929f6c6c97d1b2c61625b5ef7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53815047"
---
# <a name="manage-license-requests"></a>管理许可证请求

> [!NOTE]
> 本文中的信息仅适用于自助购买的产品。 若要了解更多信息，请参阅 [自助服务购买常见问题解答](../subscriptions/self-service-purchase-faq.yml)。

如果在组织中禁用自助服务购买，可以使用许可证请求来管理用户的许可证请求过程。 当用户尝试为已阻止的产品进行自助购买时，他们可以向管理员提交许可证请求。当他们提出请求时，他们可以添加还需要产品许可证的其他用户的姓名。

> [!NOTE]
> 如果阻止用户进行自助购买，Microsoft 不会向用户发送营销电子邮件。 此外，如果他们使用的是产品的试用版，则他们不会看到购买它的提示。 若要了解更多信息，请参阅[管理管理员 (自助服务) 。 ](../subscriptions/manage-self-service-purchases-admins.md)

若要查看和管理许可证请求，管理员使用"许可"页上的"请求 **"** 选项卡。 该列表显示所请求的产品的名称、请求许可证的人的姓名、请求的日期以及请求的状态。 管理员可以筛选列表以显示挂起或已完成的请求。 请求将进行 30 天。

## <a name="before-you-begin"></a>准备工作

你必须是全局管理员才能执行本文中的任务。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-your-own-request-process"></a>使用自己的请求过程

如果您的组织有自己的请求流程，您可以改为使用它。 创建在用户请求许可证时向用户显示的消息。

> [!IMPORTANT]
> 如果您使用自己的请求过程，则"请求"选项卡上不会 **显示任何** 请求。添加邮件之前的现有请求将继续显示，直到您批准或拒绝它们。

1. 在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。
2. 选择 **"改为使用现有请求进程"。**
3. 在右侧窗格的" **消息** "框中，键入您希望用户在请求许可证时看到的消息。 如果要同时包含指向组织策略或其他文档的链接，请在"指向文档的链接"文本框中输入 (**可选**) URL。
4. 选择“**保存**”。

返回到"请求 **"列表时**，会看到消息"**正在使用自己的许可证请求流程"。** 若要更改发送给用户的邮件，请选择"**改为使用现有请求进程"。**

## <a name="stop-using-your-own-request-process"></a>停止使用自己的请求过程

1. 在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。
2. 选择 **"改为使用现有请求进程"。**
3. 在右窗格中，清除" **使用我的组织的请求流程"** 复选框。
4. 选择“**保存**”。

## <a name="approve-or-deny-a-license-request"></a>批准或拒绝许可证请求

1. 在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。
2. 选择包含要审阅的请求的行。 右窗格显示有关哪些用户希望获得产品许可证的详细信息。
3. 若要拒绝整个请求，请选择 **"不批准"，** 在对话框中选择"**不批准"。**
4. 若要拒绝某些用户的请求，但批准其他用户，请按要删除的用户的名称选择 X。 他们的名称在"不 **分配给这些用户"下移动**。
5. 如果你有多个产品，请在"选择产品"下，选择要用于为其分配许可证的产品。
6. 若要拒绝用户访问某些应用和服务，请展开打开或关闭应用和服务，然后清除要排除的应用和服务复选框。
7. 在窗格底部，在文本框中键入可选邮件。
8. 完成后，选择"批准 **"。** 右窗格显示请求的详细信息。
9. 关闭右窗格。
    用户收到一封电子邮件，指出其请求已获得批准或拒绝。

## <a name="related-content"></a>相关内容

[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)
[将用户移动到其他订阅 (](../subscriptions/move-users-different-subscription.md) 文章) \
[购买或删除订阅许可证](buy-licenses.md) (文章) 
