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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理独立的 SharePoint Online 团队网站，添加新用户和组，删除用户和组，并创建具有自定义权限的 documents 子文件夹。
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755374"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>管理独立的 SharePoint Online 团队网站

 **摘要：** 使用这些过程管理独立的 SharePoint Online 团队网站。
  
本文介绍了独立的 SharePoint Online 团队网站的常见管理操作。
  
## <a name="add-a-new-user"></a>添加新用户

当有人新建加入网站时，您必须决定其在网站中的参与级别：
  
- 管理：将新用户帐户添加到网站管理员访问组
    
- 主动协作：将用户帐户添加到网站成员访问组
    
- 查看：将用户帐户添加到网站查看者访问组
    
如果通过 Active Directory 域服务（AD DS）管理用户帐户和组，请使用常规 AD DS 用户和组管理过程将相应的用户添加到相应的访问组，并等待与订阅的同步。
  
如果通过 Microsoft 365 管理用户帐户和组，则可以使用 Microsoft 365 管理中心或 Microsoft PowerShell：
  
- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户添加到相应的访问组。
    
- 对于 PowerShell，首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 若要将用户帐户添加到具有其用户主体名称（UPN）的访问组，请使用以下 PowerShell 命令块：
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要向具有其显示名称的访问组添加用户帐户，请使用以下 PowerShell 命令块：

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>添加新组

若要添加对整个组的访问权限，您必须确定网站中组的所有成员的参与级别：
  
- 管理：将组添加到网站管理员访问组
    
- 主动协作：将组添加到网站成员访问组
    
- 查看：将组添加到网站查看器访问组
    
如果通过 AD DS 管理用户帐户和组，请使用常规 AD DS 用户和组管理过程将适当的组添加到适当的组，并等待与订阅的同步。
  
如果您通过 Office 365 管理用户帐户和组，则可以使用 Microsoft 365 管理中心或 PowerShell：
  
- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将适当的组添加到相应的访问组。
    
- 对于 PowerShell，首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 然后，使用以下 PowerShell 命令：
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>删除用户

当必须从网站中删除某人的访问权限时，您可以从访问组中删除他们当前为其成员的访问组，具体取决于其在网站中的参与情况：
  
- 管理：从网站管理员访问组中删除用户帐户
    
- 主动协作：从网站成员访问组中删除用户帐户
    
- 查看：从网站查看器访问组中删除用户帐户
    
如果通过 AD DS 管理用户帐户和组，请使用常规 AD DS 用户和组管理过程从适当的访问组中删除相应的用户，并等待与订阅的同步。
  
如果您通过 Office 365 管理用户帐户和组，则可以使用 Microsoft 365 管理中心或 PowerShell：
  
- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的用户。
    
- 对于 PowerShell，首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
若要从具有 UPN 的访问组中删除用户帐户，请使用以下 PowerShell 命令块：
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

若要从具有显示名称的访问组中删除用户帐户，请使用以下 PowerShell 命令块：
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>删除组

若要删除对整个组的访问权限，您可以从访问组中删除其当前为其成员的访问组，这些组基于其在站点中的参与情况：
  
- 管理：从网站管理员访问组中删除组
    
- 主动协作：从网站成员访问组中删除组
    
- 查看：从网站查看器访问组中删除组
    
如果通过 Windows Server Active Directory 管理用户帐户和组，请使用常规 AD DS 用户和组管理过程从适当的访问组中删除相应的组，并等待与订阅的同步。
  
如果您通过 Office 365 管理用户帐户和组，则可以使用 Microsoft 365 管理中心或 PowerShell：
  
- 对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的组。
    
- 对于 PowerShell，首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。    
若要使用用户的显示名称从访问组中删除组，请使用以下 PowerShell 命令块：
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>使用自定义权限创建 documents 子文件夹

在某些情况下，在独立网站中工作的人员的子集需要更多的专用空间进行协作。 对于 SharePoint Online 网站，可以在网站的 "文档" 文件夹中创建一个子文件夹，并分配自定义权限。 没有权限的人员将看不到子文件夹。
  
若要创建具有自定义权限的 documents 子文件夹，请执行以下操作：
  
1. 登录到属于该网站的 "管理员" 访问组成员的帐户。 如需帮助，请参阅[在哪里登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 转到独立的团队网站，然后单击 "**文档**"。
    
3. 浏览到 "documents" 文件夹中将包含具有自定义权限的子文件夹的文件夹，创建该文件夹，然后将其打开。
    
4. 单击"共享"。
    
5. 单击 "**共享并 > 高级**"。
    
6. 单击 "**停止继承权限**"，然后单击 **"确定"**。
    
7. 单击"共享"。
    
8. 单击 "**共享并 > 高级**"。
    
9. 单击 "**授予权限 > 与 > 高级共享**"。
    
10. 在 "权限" 页上，单击** \<site name> 列表中的 "成员"**。
    
11. 在 " ** \<site name> 成员**" 页上，选中 "网站成员访问" 组旁边的复选标记，单击 "**操作**"，单击 "**从组中删除用户**"，然后单击 **"确定"**。
    
12. 若要将特定成员添加到此子文件夹，请单击 "**新建 > 添加用户**"。
    
13. 在 "**共享**" 对话框中，键入可在子文件夹中的文件上进行协作的用户帐户的名称，然后单击 "**共享**"。
    
14. 刷新网页以查看新结果。
    
15. 在左侧导航组中的 "**组**" 下，单击 " ** \<site name> 访问者**" 组，并使用步骤11-14 指定可查看子文件夹中的文件的用户帐户集（根据需要）。
    
16. 在左侧导航组中的 "**组**" 下，单击 " ** \<site name> 所有者**" 组，并使用步骤11-14 指定可在子文件夹中管理权限的用户帐户集（根据需要）。
    
17. 关闭浏览器中的 "**人员和组**" 选项卡。
    
## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)
  
[设计独立 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)



