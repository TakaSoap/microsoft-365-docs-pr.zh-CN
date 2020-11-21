---
title: 关闭你的帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: 了解如何使用 Microsoft 关闭你的帐户。
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376313"
---
# <a name="close-your-account"></a>关闭你的帐户

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。 此信息包括订阅、许可证、付款方式、用户和用户数据。

## <a name="before-you-begin"></a>准备工作

开始此过程之前，请确保备份要保留的所有数据。

您必须是全局管理员或帐单管理员才能执行本文中的任务。 有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。

## <a name="step-1-delete-users"></a>步骤1：删除用户

删除除一个全局管理员之外的所有用户。 全局管理员完成关闭帐户的步骤。 必须删除所有其他用户，然后才能在此过程结束后删除该目录。

如果用户从本地同步，请先关闭 sync，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。

若要删除用户，请参阅 <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">用户管理管理员：删除一个或多个用户</a>。

您还可以使用 <a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet 批量删除用户。

如果你的组织使用 Active Directory 与 Microsoft Azure Active Directory (Azure AD) ，请改为从 Active Directory 中删除用户帐户。 有关说明，请参阅 <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">批量删除用户在 Azure Active Directory 中</a>。

## <a name="step-2-cancel-all-active-subscriptions"></a>步骤2：取消所有活动订阅

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在 " **产品** " 选项卡上，查找 "活动订阅"。 选择“**更多操作**”（三个点），然后选择“**取消订阅**”。
3. 在“**取消订阅**”窗格中，选择取消原因。 (可选)提供反馈。
4. 选择“保存”。
5. 重复步骤1到4以取消所有活动订阅。

## <a name="step-3-delete-all-disabled-subscriptions"></a>步骤3：删除所有禁用的订阅

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在 " **产品** " 选项卡上，选择一个已禁用的订阅。
3. 在 "订阅详细信息" 页上的 " **订阅和付款设置** " 部分中，选择 " **删除订阅**"。
4. 在 " **删除订阅** " 窗格中，选择 " **删除订阅**"。
5. 在 " **删除订阅** " 对话框中，选择 **"是"**。
6. 对于每个禁用的订阅，重复步骤3到5，直到删除所有订阅。

> [!NOTE]
> 如果你无法立即删除禁用的订阅， <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">请联系支持人员</a>

## <a name="step-4-disable-multi-factor-authentication"></a>步骤4：禁用多重身份验证

1. 使用全局管理员帐户登录到管理员中心。 若要验证您拥有的角色，请参阅 [检查组织中的管理员角色](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)。
2. 转到 "**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>" 页。
3. 选择 **多因素身份验证**。
4. 在 "多重身份验证" 页上，禁用除当前正在使用的全局管理员帐户之外的所有帐户。

您还可以 <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 为多个用户禁用多重身份验证</a>。

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>步骤5：删除 Azure Active Directory 中的目录

1. 使用全局管理员帐户登录到 <a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理中心</a> 。
2. 选择“**Azure Active Directory**”。
3. 切换到要删除的组织。
4. 选择 " **删除租户**"。
5. 如果你的组织未通过一项或多项检查，你将看到有关如何传递检查的详细信息的链接。 传递所有检查后，选择 " **删除** " 以完成此过程。

完成此最后一步之后，你的 Microsoft 帐户将关闭并被删除。