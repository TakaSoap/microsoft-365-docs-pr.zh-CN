---
title: 关闭你的帐户
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
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解如何使用 Microsoft 关闭你的帐户。
ms.openlocfilehash: bbb3b56d72c0f67e7771c9a188df751aa3dd95ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594136"
---
# <a name="close-your-account"></a>关闭你的帐户

当你使用 Microsoft 关闭你的帐户时，将删除与你的帐户相关的所有信息。 此信息包括订阅、许可证、付款方式、用户和用户数据。 在开始此过程之前，请确保备份要保留的任何数据。

## <a name="step-1-delete-users"></a>步骤1：删除用户

删除除一个全局管理员之外的所有用户，以完成关闭该帐户的步骤。 必须删除所有其他用户，然后才能在此过程结束后删除该目录。

如果用户从本地同步，请先关闭 sync，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。

若要删除用户，请参阅<a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">用户管理管理员：删除一个或多个用户</a>。

您还可以使用<a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet 批量删除用户。

如果您的组织使用与 Azure AD 同步的 Active Directory，则改为从 Active Directory 中删除用户帐户。 有关说明，请参阅<a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">批量删除用户在 Azure Active Directory 中</a>。

## <a name="step-2-cancel-all-active-subscriptions"></a>步骤2：取消所有活动订阅

1. 在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。

2. 如果 "订阅" 列表位于**表格**视图中，则在右侧，选择 "**卡片**"。

3. 查找活动订阅，并在 "**设置" & "操作**" 部分，选择 "**取消订阅**"。

4. 按照提示完成此过程。

5. 重复步骤1到4以取消所有活动订阅。

## <a name="step-3-delete-all-disabled-subscriptions"></a>步骤3：删除所有禁用的订阅

1. 在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。

2. 如果 "订阅" 列表位于**表格**视图中，则在右侧，选择 "**卡片**"。

3. 在 "**订阅状态**" 旁边，选择 "**已禁用**"。

4. 查找已禁用的订阅，并在 "**设置" & "操作**" 部分，选择 "**删除**"。

5. 在 "**删除订阅**" 对话框中，选中 "**我了解影响"** 复选框，然后选择 "**删除订阅**"。

6. 对于每个禁用的订阅，重复步骤4和步骤5，直到删除所有订阅。

## <a name="step-4-disable-multi-factor-authentication"></a>步骤4：禁用多重身份验证

1. 在 "管理中心" 中，转到 "**用户** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>" 页。

2. 选择**多因素身份验证**。

3. 在 "多重身份验证" 页上，禁用除当前正在使用的全局管理员帐户之外的所有帐户。

您还可以<a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">使用 PowerShell 为多个用户禁用多重身份验证</a>。

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>步骤5：删除 Azure Active Directory 中的目录

1. 使用全局管理员帐户登录到<a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理中心</a>。

2. 选择“**Azure Active Directory**”。

3. 切换到要删除的目录。

4. 选择 "**删除目录**"。

5. 如果目录未通过一个或多个检查，则会看到有关如何传递检查的详细信息的链接。 传递所有检查后，选择 "**删除**" 以完成此过程。

完成此最后一步之后，你的 Microsoft 帐户将关闭并被删除。