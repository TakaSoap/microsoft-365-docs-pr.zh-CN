---
title: 阻止将来宾添加到特定组
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 了解如何阻止将来宾添加到特定组
ms.openlocfilehash: 8a8a62b2a320fe000580651a2577f625a9ce1b90
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064483"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>阻止将来宾添加到特定组Microsoft 365或Microsoft Teams团队

如果要允许对大多数组和团队进行来宾访问，但希望阻止某些组和团队访问来宾，可以阻止单个组和团队的来宾访问。  (通过阻止来宾访问关联组来阻止来宾访问团队。) 这将阻止添加新来宾，但不删除已加入组或团队的来宾。

如果你在你的组织中使用敏感度标签，我们建议使用它们以按组控制来宾访问。 若要了解如何执行此操作，请使用敏感度标签来保护网站Microsoft Teams、Microsoft 365[组SharePoint内容](../compliance/sensitivity-labels-teams-groups-sites.md)。 这是建议的方法。

## <a name="change-group-settings-using-microsoft-powershell"></a>使用 Microsoft PowerShell 更改组设置

您还可以使用 PowerShell 阻止向各个组添加新来宾。  (请记住，团队的关联网站SharePoint单独的[来宾](/sharepoint/change-external-sharing-site)共享控件 。) 

必须使用 [PowerShell](/powershell/azure/active-directory/install-adv2) Azure Active Directory预览版Graph (**AzureADPreview**) 更改组级别来宾访问设置：

- 如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)并按照说明安装公共预览版。

- 如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。

- 如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。

> [!NOTE]
> 您必须具有全局管理员权限才能运行这些命令。 

运行以下脚本，更改为要阻止来宾访问 */<GroupName/>* 的组的名称。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

若要验证设置，请运行此命令：

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

验证如下所示：
    
![显示来宾组访问已设置为 false 的 PowerShell 窗口屏幕截图。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)

如果要切换回此设置以允许来宾访问特定组，请运行以下脚本，更改为要允许来宾访问的 ```<GroupName>``` 组的名称。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$True
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
$id = (get-AzureADObjectSetting -TargetType groups -TargetObjectId $groupID).id
Set-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy -id $id
```

## <a name="allow-or-block-guest-access-based-on-their-domain"></a>基于其域允许或阻止来宾访问

你可以允许或阻止使用特定域的来宾。 例如，如果您的企业 (Contoso) 与另一个业务 (Fabrikam) 有合作关系，您可以将 Fabrikam 添加到允许列表中，以便您的用户可以将那些来宾添加到其组中。

有关详细信息，请参阅允许或阻止来自特定组织的 [B2B 用户的邀请](/azure/active-directory/b2b/allow-deny-list)。

## <a name="add-guests-to-the-global-address-list"></a>将来宾添加到全局地址列表

默认情况下，来宾在全局地址列表中Exchange可见。 使用下面列出的步骤使来宾在全局地址列表中可见。

通过运行以下方法查找来宾的 ObjectID：

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

然后，使用 ObjectID、GivenName、Surname、DisplayName 和 TelephoneNumber 的适当值运行以下代码。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>相关主题

[协作治理规划建议](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[创建协作管理计划](collaboration-governance-first.md)

[管理用户中的组Microsoft 365 管理中心](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory访问评审](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)
