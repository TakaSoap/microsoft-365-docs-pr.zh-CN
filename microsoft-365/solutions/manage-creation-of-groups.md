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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: 了解如何控制哪些用户可以创建Microsoft 365组。
ms.openlocfilehash: a9bfcbe97000cc6fbe0050ffee44cdc5ecc87080
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154142"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>管理可创建 Microsoft 365 组的人员

默认情况下，所有用户都可以创建Microsoft 365组。 这是推荐的方法，因为它允许用户无需 IT 协助即可开始协作。

如果您的企业要求您限制可以创建组Microsoft 365，您可以将组创建限制为特定组Microsoft 365安全组的成员。

如果你担心用户创建不符合业务标准的团队或组，请考虑要求用户完成培训课程，然后将他们添加到允许的用户组。

限制可以创建组的人时，会影响依赖组访问的所有服务，包括：

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (经典) 
- Project Web/路线图

本文中的步骤不会阻止某些角色的成员创建组。 Office 365全局管理员可以通过 Microsoft 365 管理中心、Planner、Exchange 和 SharePoint Online 创建组。 其他角色可以通过有限的方式创建组，如下所示。

- Exchange管理员：Exchange管理中心，Azure AD
- 合作伙伴第 1 层支持：Microsoft 365 管理中心、Exchange管理中心、Azure AD
- 合作伙伴第 2 层支持：Microsoft 365 管理中心、Exchange管理中心、Azure AD
- 目录编写器：Azure AD
- SharePoint管理员：SharePoint管理中心，Azure AD
- Teams服务管理员：Teams管理中心，Azure AD
- 用户管理员：Microsoft 365 管理中心，Azure AD

如果您是这些角色之一的成员，您可以为受限Microsoft 365组，然后将该用户分配为组的所有者。

## <a name="licensing-requirements"></a>许可要求

若要管理创建组的用户，以下人员Azure AD Premium分配给他们的 Azure AD 基本 EDU 许可证：

- 配置这些组创建设置的管理员
- 允许创建组的组的成员

> [!NOTE]
> 请参阅[分配或删除](/azure/active-directory/fundamentals/license-users-groups)Azure Active Directory 门户中的许可证，了解有关如何分配 Azure 许可证的更多详细信息。

以下人员不需要分配Azure AD Premium Azure AD 基本 EDU 许可证：

- 作为组Microsoft 365且无法创建其他组的人。

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>步骤 1：为需要创建组的用户创建Microsoft 365组

组织中只能有一个组可用于控制能够创建组的人。 但是，可以将其他组嵌套为此组的成员。

上述角色中的管理员无需是此组的成员：他们保留创建组的能力。

1. 在管理中心中，转到"组 ["页面](https://admin.microsoft.com/adminportal/home#/groups)。

2. 单击"**添加组"。**

3. 选择您想要的组类型。 请记住该组的名称！ 稍后需要用到该名称。

4. 完成组设置，添加要能够在组织内创建组的人或其他组。

有关详细说明，请参阅创建[、编辑或删除](../admin/email/create-edit-or-delete-a-security-group.md)安全Microsoft 365 管理中心。

## <a name="step-2-run-powershell-commands"></a>步骤 2：运行 PowerShell 命令

你必须使用 Azure Active Directory [PowerShell for Graph (AzureAD](/powershell/azure/active-directory/install-adv2))  (模块名称 **AzureADPreview**) 的预览版本来更改组级别的来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

将下面的脚本复制到文本编辑器（如 记事本 或[Windows PowerShell ISE 中](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)）。

将 *\<GroupName\>* 替换为您创建的组的名称。 例如：

`$GroupName = "Group Creators"`

将文件另存为GroupCreators.ps1。

在 PowerShell 窗口中，导航到保存文件的位置 <FileLocation> ， ("CD") 。

通过键入以下命令运行脚本：

`.\GroupCreators.ps1`

[，当系统提示时，使用](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)管理员帐户登录。

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

![PowerShell 脚本输出的屏幕截图。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

如果将来要更改使用哪个组，可以使用新组的名称重新运行脚本。

如果要关闭组创建限制，并再次允许所有用户创建组，$GroupName设置为""，$AllowGroupCreation设置为"True"，然后重新运行脚本。

## <a name="step-3-verify-that-it-works"></a>步骤 3：验证有效性

更改可能需要 30 分钟或更多时间才能生效。 可以通过执行以下操作来验证新设置：

1. 使用Microsoft 365创建组的用户的用户帐户登录。 即，他们不是你创建的组的成员或管理员。

2. 选择 **Planner** 磁贴。

3. 在 Planner 中， **选择** 左侧导航栏中的"新建计划"以创建计划。

4. 应收到一条消息，指出已禁用计划和组创建。

请再次与组的成员尝试相同的过程。

> [!NOTE]
> 如果组的成员无法创建组，请检查他们是否未通过 OWA 邮箱策略 [被阻止](/powershell/module/exchange/set-owamailboxpolicy)。

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[Office 365 PowerShell 入门](../enterprise/getting-started-with-microsoft-365-powershell.md)

[在"管理中心"中设置自助服务Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[用于配置组设置的 Azure Active Directory cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
