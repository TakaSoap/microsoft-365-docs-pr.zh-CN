---
title: 管理计费通知和发票附件
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 了解如何管理接收帐单通知电子邮件和发票附件的人。
ms.openlocfilehash: f0811c5d027d042b5114c9e05c698dab1e08763b
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515217"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>管理计费通知和发票附件

通过 **"** 帐单通知"页，你可以管理接收组织帐单通知电子邮件的人。 该页面还提供将组织发票作为电子邮件附件 [接收的选项](#receive-your-organizations-invoices-as-email-attachments)。

## <a name="before-you-begin"></a>开始之前

你必须是全局管理员才能执行本文中所述的步骤。 计费管理员可以进行其中一些更改，如以下各节所述。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="change-the-language-you-receive-email-in"></a>更改接收电子邮件的语言

> [!NOTE]
> 帐单管理员还可以执行本节中的步骤。

帐单通知电子邮件以组织的首选语言发送。 若要更改首选语言，请使用以下步骤。

1. 在 Microsoft 365 管理中心，转到"**计费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">通知"</a>页。
2. 在"**帐单通知设置**"部分，选择 **"编辑通知设置"。**
3. 在 **"计费通知设置**"窗格中，在 **"** 首选语言"下，选择想要使用的语言，然后选择"**保存"。**

## <a name="change-who-receives-billing-notifications"></a>更改接收帐单通知的人

组织的帐单通知将发送到每个全局管理员和帐单管理员的主电子邮件地址和备用电子邮件地址。若要更改哪些用户具有全局管理员或帐单管理员角色，请使用以下步骤。

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>使用"计费通知"页分配管理员角色

1. 在管理中心中，转到“**账单**”  >  “<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">账单通知</a>”页面。
2. 在 **"管理员接收帐单通知**"部分，在说明文本中选择"计费管理员 **"或"** 全局管理员"链接。
3. 在右侧窗格中的"已分配 **管理员"** 选项卡上，选择"**添加"。**
4. 在 **"添加管理员** "窗格中，键入显示名称或用户名，然后从建议列表中选择用户。
5. 添加多个用户，直到完成。
6. 选择“保存”。 用户将添加到已分配的管理员列表中。

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>使用"计费通知"页删除管理员角色

1. 在管理中心中，转到“**账单**”  >  “<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">账单通知</a>”页面。
2. 在 **"管理员接收帐单通知**"部分，在说明文本中选择"计费管理员 **"或"** 全局管理员"链接。
3. 在右侧窗格中的"已分配管理员 **"选项卡上**，选择要从角色中删除的用户，然后选择"删除 **"。**
4. 在确认框中，选择"删除 **"。** 将从分配的管理员列表中删除用户。

## <a name="change-the-email-addresses-for-admins"></a>更改管理员的电子邮件地址

若要更改组织中其他管理员的主电子邮件地址和备用电子邮件地址，请使用以下步骤。

> [!NOTE]
> 计费管理员可以更改自己的主电子邮件地址和备用电子邮件地址，但不能更改其他管理员的电子邮件地址。

1. 在管理中心中，转到“**账单**”  >  “<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">账单通知</a>”页面。
2. 在 **"管理员接收帐单通知"部分中** ，选择一个名称。
3. 在右侧窗格中，根据需要添加或更新主电子邮件地址和备用电子邮件地址，然后选择"保存 **"。**

## <a name="change-your-organizations-contact-email"></a>更改组织的联系人电子邮件

除了全局管理员和帐单管理员外，我们还向组织的联系人电子邮件地址发送帐单通知。 若要更改电子邮件地址，请使用以下步骤。

1. 在管理中心中，转到“**账单**”  >  “<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">账单通知</a>”页面。
2. 在 **"接收计费通知的组织联系人"下**，选择组织联系人。
3. 在右侧窗格中，键入想要使用的电子邮件地址，然后选择"保存 **"。**

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>以电子邮件附件接收组织的发票

> [!NOTE]
> 帐单管理员还可以执行本节中的步骤。

在准备好新发票时，可以将组织的发票副本作为 PDF 文件附加到发票通知电子邮件中。 使用以下步骤接收作为附件的发票。

1. 在管理中心中，转到“**账单**”  >  “<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">账单通知</a>”页面。
2. 在 **"帐单通知设置"下**，**选择"编辑通知设置"。**
3. 在 **"帐单通知设置**"窗格中的 **"将 PDF 附加到发票** 电子邮件"下，选中复选框，然后选择"保存 **"。**

若要随时停止接收发票附件，请按照上述步骤操作，并清除步骤 3 中的"将 **PDF** 附加到发票电子邮件"复选框。

## <a name="what-if-i-have-a-billing-profile"></a>如果我有计费配置文件，该做什么？

如果你有计费配置文件，则本文中介绍的一些步骤对于你的某些订阅可能略有不同。 本节介绍这些差异。 [我如何知道我是否具有计费配置文件？](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>谁接收帐单通知？

帐单通知电子邮件将发送到分配了以下角色之一的用户的主电子邮件地址和备用电子邮件地址：

- 计费配置文件所有者
- 计费配置文件参与者
- 发票经理

若要了解有关计费配置文件角色以及如何管理它们的信息，请参阅了解 Azure 中的 [Microsoft 客户协议管理角色](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles)。

若要更改接收组织帐单通知的用户，请使用以下步骤更改分配给用户的角色。

1. 在管理中心，转到"帐单&  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">付款</a>页面。
2. 在" **计费配置文件"** 选项卡上，选择计费配置文件。
3. 在"**计费配置文件角色**"部分中，为计费配置文件所有者、计费配置文件参与者或发票经理分配 **或删除角色**。

### <a name="receive-invoices-as-email-attachments"></a>接收发票作为电子邮件附件

若要将发票作为发票通知的附件接收，请使用以下步骤为特定计费配置文件启用此设置。

1. 在管理中心，转到"帐单&  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">付款</a>页面。
2. 选择 **"计费配置文件"** 选项卡，然后从列表中选择计费配置文件。
3. 在计费配置文件详细信息页面上，在"**获取电子邮件附件中的** 发票"下，将开关 **切换到"打开"。**

## <a name="related-content"></a>相关内容

[查看帐单或发票 (](view-your-bill-or-invoice.md) 文章) \
[了解 Microsoft 365 商业版](understand-your-invoice2.md) 帐单或 (文章) \
[添加用户并同时分配许可证 (](../../admin/add-users/add-users.md) 文章) 