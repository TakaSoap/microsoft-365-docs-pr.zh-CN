---
title: 管理可以创建 Microsoft 365 组的用户
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 了解如何控制哪些用户可以创建 Microsoft 365 组。
ms.openlocfilehash: f2b2837a762398bb065d36c7f849b2fdcbbb5816
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788880"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>管理可以创建 Microsoft 365 组的用户

默认情况下，所有用户都可以创建 Microsoft 365 组。 这是建议的方法，因为它允许用户在不需要帮助的情况下开始协作。

如果您的业务要求您限制谁可以创建组，则可以按照本文中的过程操作。 当您限制可以创建组的用户时，它会影响依赖于访问组的所有服务，包括：

- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI (经典) 
    
- Web/路线图的项目
    
您可以将 Microsoft 365 组创建限制为特定安全组的成员。 若要配置此设置，请使用 Windows PowerShell。 本文将引导您完成所需的步骤。
  
本文中的步骤不会阻止某些角色的成员创建组。 Office 365 全局管理员可以通过任何方式创建组，例如 Microsoft 365 管理中心、Planner、团队、Exchange 和 SharePoint Online。 其他角色可以通过有限的方法创建组，如下所示。
        
  - Exchange 管理员： Exchange 管理中心、Azure AD
    
  - 合作伙伴第1层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD
    
  - 合作伙伴第2层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD
    
  - 目录写入程序： Azure AD

  - SharePoint 管理员： SharePoint 管理中心、Azure AD
  
  - 团队服务管理员：团队管理员中心、Azure AD
  
  - 用户管理管理员： Microsoft 365 管理中心、Yammer、Azure AD
     
如果您是上述某个角色的成员，则可以为受限制的用户创建 Microsoft 365 组，然后将该用户分配为该组的所有者。

## <a name="licensing-requirements"></a>许可要求

若要管理创建组的人员，以下人员需要分配给它们的 Azure AD Premium 许可证或 Azure AD 基本 EDU 许可证：

- 配置这些组创建设置的管理员
- 允许创建组的安全组的成员
 
> [!NOTE]
> 有关如何分配 Azure 许可证的更多详细信息，请参阅 [在 Azure Active Directory 门户中分配或删除许可证](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 。

以下人员不需要为其分配 Azure AD Premium 或 Azure AD 基本 EDU 许可证：

- 属于 Microsoft 365 组成员并不能创建其他组的人员。

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>步骤1：为需要创建 Microsoft 365 组的用户创建安全组

您的组织中仅有一个安全组可用于控制能够创建组的用户。 但是，你可以将其他安全组包含在内作为该组的成员。

上面列出的角色中的管理员不需要是该组的成员：它们保留了其创建组的能力。

> [!IMPORTANT]
> 请务必使用 **安全组** 来限制可以创建组的用户。 不支持使用 Microsoft 365 组。 
    
1. 在管理中心，转到 "组" [页面](https://admin.microsoft.com/adminportal/home#/groups)。

2. 单击 " **添加组**"。

3. 选择 " **安全** " 作为组类型。 请记住该组的名称！ 稍后需要用到该名称。
  
4. 完成设置安全组，添加你希望能够在你的组织中创建组的人员或其他安全组。
    
有关详细说明，请参阅 [在 Microsoft 365 管理中心中创建、编辑或删除安全组](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)。
 
## <a name="step-2-run-powershell-commands"></a>步骤 2：运行 PowerShell 命令

您必须使用预览版 of [Graph For Graph (AzureAD) ](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模块名称 **AzureADPreview**) 以更改组级别的来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

将下面的脚本复制到文本编辑器（如记事本）或 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)中。

*\<SecurityGroupName\>* 将替换为您创建的安全组的名称。 例如：

`$GroupName = "Group Creators"`

将文件另存为 GroupCreators.ps1。 

在 PowerShell 窗口中，导航到保存文件的位置 (键入 "CD <FileLocation> " ) 。

通过键入以下命令运行脚本：

`.\GroupCreators.ps1`

出现提示时， [使用管理员帐户登录](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) 。

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

脚本的最后一行将显示更新的设置：

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

如果将来您想要更改所使用的安全组，则可以使用新安全组的名称重新运行脚本。

如果要关闭组创建限制，并再次允许所有用户创建组，请将 $GroupName 设置为 "" 并 $AllowGroupCreation 为 "True"，然后重新运行该脚本。
    
## <a name="step-3-verify-that-it-works"></a>步骤 3：验证有效性

更改可能需要30分钟或更长时间才能生效。 您可以通过执行以下操作来验证新设置：

1. 使用无法创建组的用户的用户帐户登录到 Microsoft 365。 也就是说，它们不是您创建的安全组的成员，也不是管理员的成员。
    
2. 选择 " **Planner** " 磁贴。 
    
3. 在 Planner 中，选择左侧导航中的 " **新建计划** " 以创建一个计划。 
  
4. 您应该会收到一条消息，指出计划和组创建已禁用。

请使用安全组的成员再次尝试相同的过程。

> [!NOTE]
> 如果安全组的成员无法创建组，请检查它们是否通过 [OWA 邮箱策略](https://go.microsoft.com/fwlink/?linkid=852135)被阻止。
    
## <a name="related-articles"></a>相关文章

[Office 365 PowerShell 入门](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[在 Azure Active Directory 中设置自助服务组管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
