---
title: 管理可创建 Microsoft 365 组的人员
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 了解如何控制哪些用户可以创建 Microsoft 365 组。
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819698"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>管理可创建 Microsoft 365 组的人员

默认情况下，所有用户都可以创建 Microsoft 365 组。 这是推荐的方法，因为它允许用户无需 IT 协助即可开始协作。

如果您的企业要求您限制可以创建组的人，您可以按照本文中的过程操作。 限制可以创建组的人时，会影响依赖组访问的所有服务，包括：

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (经典) 
- Project 网页/路线图

你可以将 Microsoft 365 组创建限制为特定 Microsoft 365 组或安全组的成员。 若要配置此配置，请使用Windows PowerShell。 本文将指导你完成所需步骤。

本文中的步骤不会阻止某些角色的成员创建组。 Office 365 全局管理员可以通过任何方式（如 Microsoft 365 管理中心、Planner、Teams、Exchange 和 SharePoint Online）创建组。 其他角色可以通过有限的方式创建组，如下所示。

- Exchange 管理员：Exchange 管理中心，Azure AD
- 合作伙伴层 1 支持：Microsoft 365 管理中心、Exchange 管理中心、Azure AD
- 合作伙伴层 2 支持：Microsoft 365 管理中心、Exchange 管理中心、Azure AD
- 目录编写器：Azure AD
- SharePoint 管理员：SharePoint 管理中心、Azure AD
- Teams 服务管理员：Teams 管理中心、Azure AD
- 用户管理员：Microsoft 365 管理中心，Azure AD

如果你是其中一个角色的成员，你可以为受限用户创建 Microsoft 365 组，然后将该用户分配为组的所有者。

## <a name="licensing-requirements"></a>许可要求

若要管理创建组的用户，以下人员需要分配给他们的 Azure AD Premium 许可证或 Azure AD Basic EDU 许可证：

- 配置这些组创建设置的管理员
- 允许创建组的组的成员

> [!NOTE]
> 若要 [详细了解如何分配 Azure 许可证，请参阅在 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 门户中分配或删除许可证。

以下人员不需要分配给他们的 Azure AD Premium 或 Azure AD Basic EDU 许可证：

- 作为 Microsoft 365 组的成员且无法创建其他组的人。

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>步骤 1：为需要创建 Microsoft 365 组的用户创建组

组织中只能有一个组可用于控制能够创建组的人。 但是，可以将其他组嵌套为此组的成员。

上述角色中的管理员无需是此组的成员：他们保留创建组的能力。

1. 在管理中心中，转到"组 ["页面](https://admin.microsoft.com/adminportal/home#/groups)。

2. 单击"**添加组"。**

3. 选择您想要的组类型。 请记住该组的名称！ 稍后需要用到该名称。

4. 完成组设置，添加要能够在组织内创建组的人或其他组。

有关详细说明，请参阅在 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)管理中心创建、编辑或删除安全组。

## <a name="step-2-run-powershell-commands"></a>步骤 2：运行 PowerShell 命令

必须使用 Azure [Active Directory PowerShell graph (AzureAD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2))  (模块名称 **AzureADPreview**) 预览版更改组级别来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

将下面的脚本复制到文本编辑器（如记事本）或 [ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)Windows PowerShell中。

将 *\<GroupName\>* 替换为您创建的组的名称。 例如：

`$GroupName = "Group Creators"`

将文件另存为GroupCreators.ps1。

在 PowerShell 窗口中，导航到保存文件的位置， ("CD <FileLocation> ") 。

通过键入以下命令运行脚本：

`.\GroupCreators.ps1`

[，当系统提示时，使用](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)管理员帐户登录。

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

如果将来要更改使用哪个组，可以使用新组的名称重新运行脚本。

如果要关闭组创建限制，并再次允许所有用户创建组，$GroupName设置为""，$AllowGroupCreation设置为"True"，然后重新运行脚本。

## <a name="step-3-verify-that-it-works"></a>步骤 3：验证有效性

更改可能需要 30 分钟或更多时间才能生效。 可以通过执行以下操作来验证新设置：

1. 使用不应能够创建组的用户的用户帐户登录到 Microsoft 365。 即，他们不是你创建的组的成员或管理员。

2. 选择 **Planner** 磁贴。

3. 在 Planner 中， **选择** 左侧导航栏中的"新建计划"以创建计划。

4. 应收到一条消息，指出已禁用计划和组创建。

请再次与组的成员尝试相同的过程。

> [!NOTE]
> 如果组的成员无法创建组，请检查他们是否未通过 OWA 邮箱策略 [被阻止](https://go.microsoft.com/fwlink/?linkid=852135)。

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[Office 365 PowerShell 入门](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[在 Azure Active Directory 中设置自助服务组管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
