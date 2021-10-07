---
title: 关闭帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
- AdminTemplateSet
search.appverid: MET150
description: 关闭 Microsoft 帐户时，将删除与帐户相关的所有信息，包括许可证、用户和用户数据。
ms.date: 04/02/2021
ms.openlocfilehash: b19328ffaf785479b81d6253c602c8f80fca99ae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202017"
---
# <a name="close-your-account"></a>关闭帐户

当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。 此信息包括订阅、许可证、付款方式、用户和用户数据。

## <a name="before-you-begin"></a>准备工作

开始此过程之前，请确保备份要保留的所有数据。

你必须是全局管理员或帐单管理员才能执行本文中的任务。 有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。

## <a name="step-1-delete-users"></a>步骤 1：删除用户

删除除一个全局管理员以外的所有用户。 全局管理员完成关闭帐户的步骤。 在此过程结束时，必须先删除所有其他用户，然后才能删除该目录。

如果用户从本地同步，请首先关闭同步，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。

若要删除用户，请参阅用户 [管理管理员：删除一个或多个用户](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365)。

您还可以使用 [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet 批量删除用户。

如果你的组织使用与 Azure AD Microsoft Azure Active Directory (同步的 Active Directory) ，请改为从 Active Directory 中删除用户帐户。 有关说明，请参阅批量[删除用户Azure Active Directory。](/azure/active-directory/users-groups-roles/users-bulk-delete)

## <a name="step-2-cancel-all-active-subscriptions"></a>步骤 2：取消所有活动订阅

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在" **产品"** 选项卡上，查找活动订阅。 选择三个点（更多操作），然后选择“**取消订阅**”。
3. 在“**取消订阅**”窗格中，选择取消原因。可选择提供任何反馈。
4. 选择“**保存**”。
5. 重复步骤 1 至 4 以取消所有活动订阅。

## <a name="step-3-delete-all-disabled-subscriptions"></a>步骤 3：删除所有已禁用的订阅

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在" **产品"** 选项卡上，选择已禁用的订阅。
3. 在订阅详细信息页面上的 **订阅和付款** 设置部分中，选择删除 **订阅**。
4. 在"**删除订阅"窗格中**，选择"**删除订阅"。**
5. 在"**删除订阅**"对话框中，选择"**是"。**
6. 对于每个已禁用的订阅，重复步骤 3 至 5，直到删除所有订阅。

> [!NOTE]
> 如果无法立即删除已禁用的订阅，请联系 [支持人员](../business-video/get-help-support.md)。

## <a name="step-4-disable-multi-factor-authentication"></a>步骤 4：禁用多重身份验证

1. 使用全局管理员帐户登录管理中心。 若要验证你拥有的角色，请参阅 [检查你的组织的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。
2. 转到"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">""活动用户"</a>页。
3. 选择 **"多重身份验证"。**
4. 在多重身份验证页面上，禁用除当前使用的全局管理员帐户之外的所有帐户。

您还可以使用 [PowerShell 为多个用户禁用多重身份验证](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)。


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>步骤 5：删除Azure Active Directory

1. 使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">Azure AD</a> 管理中心。
2. 选择“**Azure Active Directory**”。
3. 切换到要删除的组织。
4. 选择 **"删除租户"。**
5. 如果您的组织未能通过一项或多项检查，则会看到一个链接，该链接指向有关通过检查详细信息。 通过所有检查后，选择" **删除** "以完成此过程。

完成最后一步后，Microsoft 帐户将关闭并删除。

## <a name="related-content"></a>相关内容 

[了解适用于企业Microsoft 365的](./billing-and-payments/understand-your-invoice2.md)帐单 (发票) \
[取消订阅 (](./subscriptions/cancel-your-subscription.md) 文章) 

