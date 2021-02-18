---
title: 管理独立的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理独立的 SharePoint Online 团队网站、添加新用户和组、删除用户和组以及创建具有自定义权限的文档子文件夹。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289517"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理独立的 SharePoint Online 团队网站

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1](office-365-atp.md)
- SharePoint Online 

 **摘要：** 通过这些过程管理独立的 SharePoint Online 团队网站。

本文介绍了独立 SharePoint Online 团队网站的常见管理操作。

## <a name="add-a-new-user"></a>添加新用户

当有人新加入网站时，您必须确定其参与网站的级别：

- 管理：将新用户帐户添加到网站管理员访问组

- 活动协作：将用户帐户添加到网站成员访问组

- 查看：将用户帐户添加到网站查看者访问组

如果要通过 Active Directory 域服务 (AD DS) 管理用户帐户和组，则使用正常的 AD DS 用户和组管理过程将相应的用户添加到相应的访问组，并等待与订阅同步。

如果通过 Microsoft 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 Microsoft PowerShell：

- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户添加到相应的访问组。

- 对于 PowerShell，首先 [使用适用于 Graph 模块的 Azure Active Directory PowerShell 进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。 若要将用户帐户添加到其用户主体名称为 UPN (访问) ，请使用以下 PowerShell 命令块：

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要将用户帐户添加到具有其权限显示名称，请使用以下 PowerShell 命令块：

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>添加新组

若要添加对整个组的访问权限，您必须确定网站中组所有成员的参与级别：

- 管理：将组添加到网站管理员访问组

- 活动协作：将组添加到网站成员访问组

- 查看：将组添加到网站查看者访问组

如果通过 AD DS 管理用户帐户和组，则使用正常的 AD DS 用户和组管理过程将相应的组添加到相应的组，并等待与订阅同步。

如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：

- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的组添加到相应的访问组。

- 对于 PowerShell，首先 [使用适用于 Graph 模块的 Azure Active Directory PowerShell 进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 然后，使用以下 PowerShell 命令：

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>删除用户

当必须从网站中删除某人的访问权限时，根据用户对网站的参与情况，将其从当前是访问组的成员中删除：

- 管理：从网站管理员访问组中删除用户帐户

- 活动协作：从网站成员访问组中删除用户帐户

- 查看：从网站查看者访问组中删除用户帐户

如果通过 AD DS 管理用户帐户和组，则使用正常的 AD DS 用户和组管理过程从相应的访问组中删除相应的用户，并等待与订阅同步。

如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：

- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的用户。

- 对于 PowerShell，首先 [使用适用于 Graph 模块的 Azure Active Directory PowerShell 进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
若要从具有其 UPN 的访问组中删除用户帐户，请使用以下 PowerShell 命令块：

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要从访问组中删除用户帐户及其显示名称，请使用以下 PowerShell 命令块：

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>删除组

若要删除整个组的访问权限，请根据用户对网站的参与情况，从当前他们作为访问组的成员的访问组中删除该组：

- 管理：从网站管理员访问组中删除组

- 活动协作：从网站成员访问组中删除组

- 查看：从网站查看者访问组中删除组

如果要通过 Windows Server Active Directory 管理用户帐户和组，则使用正常的 AD DS 用户和组管理过程从相应的访问组中删除相应的组，并等待与订阅同步。

如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：

- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的组。

- 对于 PowerShell，首先 [使用适用于 Graph 模块的 Azure Active Directory PowerShell 进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
若要使用其显示名称从访问组中删除组，请使用以下 PowerShell 命令块：

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>使用自定义权限创建文档子文件夹

在某些情况下，在独立网站中工作的一部分人员需要一个更为私人的协作位置。 对于 SharePoint Online 网站，您可以在网站的"文档"文件夹中创建子文件夹并分配自定义权限。 没有权限的用户将看不到子文件夹。

若要创建具有自定义权限的文档子文件夹，请执行下列操作：

1. 登录到作为网站的管理员访问组的成员的帐户。 如需帮助，请参阅[在哪里登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 转到独立团队网站，然后单击"**文档"。**

3. 浏览到将包含具有自定义权限的子文件夹的文档文件夹中的文件夹，创建该文件夹，然后打开它。

4. 单击“**共享**”。

5. 单击 **"与>共享"。**

6. 单击 **"停止继承权限"，** 然后单击"**确定"。**

7. 单击“**共享**”。

8. 单击 **"与>共享"。**

9. 单击 **"授予与>共享的权限>"。**

10. 在"权限"页上，单击 **\<site name> 列表中的"成员"。**

11. 在"**\<site name> 成员**"页上，选择网站成员访问组旁边的选中标记，单击"操作"，单击"从组中删除 **用户**"，然后单击"**确定"。**

12. 若要向此子文件夹添加特定成员，请单击">**添加用户"。**

13. 在 **"共享**"对话框中，键入可以在子文件夹内对文件进行协作的用户帐户的名称，然后单击"**共享"。**

14. 刷新网页以查看新结果。

15. 在左侧导航中的"组"下，单击 **\<site name> Visitors** 组并使用步骤 11-14 指定一组用户帐户，这些用户帐户可根据需要查看子 (文件) 。

16. 在左侧导航中的"组"下，**\<site name>** 单击"所有者"组并使用步骤 11-14 指定一组用户帐户，这些用户帐户可根据需要管理子 (权限) 。

17. 关闭 **浏览器中的"人员** "和"组"选项卡。

## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)

[设计独立 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)
